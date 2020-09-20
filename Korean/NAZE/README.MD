# Deplux NAZE
## 페이지
 * [Home](./../README.MD)
 * [config.json](./../Config/README.MD)
 * [Deplux NAZE](./../NAZE/README.MD)

## Description
봇 호스팅 서비스로 강력한 봇을 만들어보세요.

### 도전해 보세요 :
#### Create NAZE Hosting
NAZE 호스팅은 별도의 설정 파일을 필요로 합니다, 한번 따라해 보세요 :   
 1. 일반적인 호스팅을 생성하고 활성화
 2. Deploy할 최상위 디렉터리에 `.naze`라는 이름의 디렉터리 생성
 3. 해당 경로에 `manifest.json` 파일 생성 :
 ```json
{
    "Main":"./YOUR SCRIPT FILENAME HERE",
    "Token":"YOUR DISCORD BOT TOKEN HERE"
    // 추후에 매개변수를 지원할 수도 있습니다
}
 ```
 4. 해당 경로에 봇을 구동할 javascript 코드 작성 :
```javascript
const client = new Discord.Client(); // You don't have to require discord.js

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
});

client.on('message', msg => {
  if (msg.content === 'ping') {
    msg.reply('Pong!');
  }
});

client.login(Token); // "Token" is a public constant what you wrote in manifest.json
 ```
 5. Deploy하기
    * .zip으로 압축하여 배포
    * config.json으로 Git repository가 설정되어 있다면 Github 등으로 배포
 6. 봇이 성공적으로 작동합니다!

### NAZE Plugin
NAZE 서비스는 안정적인 Discord 봇 호스팅을 위해 Team Deplux가 지정한 플러그인만 허용합니다.   
이러한 플러그인들은 전역 변수로 제공되며, 아래와 같은 플러그인(또는 라이브러리)를 지원합니다. (Discord.js는 최상위 전역변수로 제공)

 * Free plan
    * [path](https://nodejs.org/api/path.html)[^1]
    * Storage[^2]
    * [moment](https://momentjs.com/)[^1]
    * Utils[^2]

 * Premium plan
    * [Komoran](https://github.com/shineware/KOMORAN)[^2]
    * [mysql](https://www.npmjs.com/package/mysql2)[^1]
    * Neural[^2]
    * [request](https://github.com/request/request)[^1]

 [^1]: 기존 라이브러리의 API와 동일
 [^2]: 자체제작 또는 변형된 라이브러리

또한 두 라이브러리(플러그인)은 아래와 같이 불러올 수 있습니다.

```javascript
const MomentJS = Plugins.moment // you can import free plugin with "Plugins"
const Komoran = Premium.Komoran // you can import premium plugin with "Premium"
```

#### 자체제작/변형 라이브러리 문서
자체제작 또는 변형한 라이브러리에 대한 문서 및 리스트입니다.

#### Deplux 서드파티 개발자
별도의 라이브러리를 사용하고 싶거나 본인이 개발한 라이브러리를 Deplux 인증 라이브러리로 등록하고 싶다면 Team Deplux로 연락주세요,   
라이브러리 심사 후 Deplux에 등록해 드립니다!