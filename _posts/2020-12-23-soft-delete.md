---
layout: post
title: Soft Delete
categories: [ Tech ]
tags: [ database ]
permalink: /:categories/:title/
---

### Soft Delete 개념

* DB의 데이터 삭제 요청 시 row를 그대로 제거하지 않고 `deletedAt`과 같은 별도의 column을 두어 삭제 여부만 기록하는 방식  
* Soft delete를 사용하는 테이블의 경우 데이터 조회 시 기본적으로 `deletedAt`을 확인하는 별도의 로직이 필요함  
* 장단점이 있기 때문에 tradeoff를 고려하여 반드시 필요한 경우에 사용하는 것이 좋음
  * 장점: 삭제된 데이터에 대한 정보가 추후에 필요한 경우, 삭제 이력 확인 및 필요 시 데이터 복구 용이함
  * 단점: 데이터 조회 및 테이블 간 join 연산 등 수행할 때 추가적인 오버헤드 있음

### Node.js Sequelize에서 Soft Delete 활용하기
Sequelize는 `paranoid table`을 통해 soft delete를 지원함. Sequelize Doc에서 soft delete 개념을 다음과 같이 설명함

[Paranoid](https://sequelize.org/master/manual/paranoid.html)
> Sequelize supports the concept of paranoid tables. A paranoid table is one that, when told to delete a record, it will not truly delete it. Instead, a special column called deletedAt will have its value set to the timestamp of that deletion request. This means that paranoid tables perform a soft-deletion of records, instead of a hard-deletion.

> Sequelize는 paranoid 테이블 개념을 지원한다. Paranoid 테이블이란 레코드 삭제 요청 시 온전하게 삭제하지 않는 대신 deletedAt이라는 특별한 열에 삭제 요청 시간을 표시한다. 이는 paranoid 테이블이 레코드의 hard-deletion이 아닌 soft-deletion을 수행함을 의미한다. 

#### Table 정의
Sequelize로 테이블 정의 시 `paranoid` 옵션을 명시할 수 있음
```javascript
class Post extends Model {}
Post.init({ /* attributes here */ }, {
  sequelize,
  paranoid: true,
});
```

#### Record 삭제
Sequelize의 `destroy` 명령 통해 테이블의 row 삭제 시 `deletedAt` 칼럼의 값이 삭제 요청 시점의 timestamp로 지정됨
```javascript
await Post.destroy({
  where: {
    id: 1
  }
});
// UPDATE "posts" SET "deletedAt"=[timestamp] WHERE "deletedAt" IS NULL AND "id" = 1
```
Paranoid 테이블에 대한 hard-deletion도 가능함: `destroy` 명령에 `force: true` 옵션을 명시하면 row가 hard delete 됨
```javascript
await Post.destroy({
  where: {
    id: 1
  },
  force: true
});
// DELETE FROM "posts" WHERE "id" = 1
```

### 참고자료
* <https://stackoverflow.com/questions/2549839/are-soft-deletes-a-good-idea>
* <https://sequelize.org/master/manual/paranoid.html>