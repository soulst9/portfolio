# 포트폴리오입니다. 

# 자기소개

**Javascript** 에 매료되어 Node.js를 통해 웹에 입문하였고, 클라이언트 개발자에서 서버개발자로 완벽히 전향하였습니다.

제 스스로 만족할 수 있는 코드를 만들기 위해 끊임없이 고민하는 개발자가 되고 싶습니다.



# 최근 관심 분야

`마이크로 서비스`, `docker`, `함수형 프로그래밍` 등



# 해왔던 일

[U+ 산업용직캠](http://www.uplus.co.kr/biz/m2m/mmtom/InitBzMtmmLc.hpi) 서비스 솔루션에서 웹 개발을 담당하였습니다. 

솔루션은 `node.js express`, `mysql`, `socket-io`, `fcm` 등의 프레임워크 및 라이브러리가 사용되었습니다.



# github에서 개인 프로젝트 진행 중

1. [오브젝트 쿼리](https://github.com/soulst9/jsQuery)

Object 타입의 지원으로 인해 수많은 요청이 Object 타입으로 이루어져있고 그것을 다시 string 타입의 쿼리로 변경해야 하는 것에 착안하여 프로젝트 시작하였습니다.

아래의 예시처럼, **오브젝트 쿼리**는 미리 정의된 Keyword를 갖는 **Key**와 **Value**로 이루어져 있습니다.

```
/**
 * 조회 예시입니다.
 */
const example1 = jsQuery.selectQuery(
  {
    select: ["_id", "idx", "name"],
    from: { 
      table: "tb_products"
    },
    where: {
      _id: 1
    },
    groupby: [
      "idx",
      "name"
    ],
    orderby: [
      "idx",
      "name"
    ]
  }
);
```

현재는, Mysql 쿼리로 변경하는 것에 대해서만 지원하고 있고, 모든 기능을 갖고 있는 것은 아닙니다.

좀 더 많은 예시는 [링크](https://github.com/soulst9/jsQuery)를 참조해주세요.

2. [이미지 서버](https://github.com/soulst9/image_server)

이미지 서버의 개발을 고려할 때 사용자가 늘어감에 따라 기하급수적으로 늘어나는 서버용량을 고민하지 않을 수가 없습니다.

On-demand 방식의 이미지 서버를 생각하여 진행한 프로젝트입니다.

실시간으로 이미지를 리사이징하여 응답을 줘야 하기 때문에 속도가 중요하지 않을 수 없습니다.

그래서 **sharp**모듈을 사용하였습니다. 기존의 **ImageMagic**에 몇 배의 빠른 속도로 일을 해내기 때문에 시험적으로 사용해볼 수 있었

고 결과는 만족스러웠습니다.

```
/*
 * sharp는 Promise를 지원하기 때문에 async/await를 사용할 수 있습니다.
 */

const saveImages = async (filepath, files) => {
  let resultAll = [];
  for (const file of files) {
    const result = await savetoWebp(filepath, file);
    if (result) {
      result.originalname = file.originalname;
      result.originalformat = extention(file.originalname);
      result.finalname = rename(file.originalname);
      result.filepath = symboliclink(filepath);
      resultAll.push(result);
    }
  }
  return resultAll;
};

const savetoWebp = (filepath, file) => {
  return sharp(file.buffer)
    .webp({ alphaQuality: 60 })
    .toFile(path.join(filepath, rename(file.originalname)))
    .catch(err => {
      console.log(err);
    });
};
```



3. 그 밖의 비공개 프로젝트
   * Flutter로 만드는 앱 개발 진행 중 ...
   * sequilize 모듈과 비슷한 형태의 개인 라이브러리 개발 중...







contact: 010-8918-1281

email: banzry@nate.com



