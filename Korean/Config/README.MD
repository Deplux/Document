# config.json 사용법
## 페이지
 * [Home](./../README.MD)
 * [config.json](./../Config/README.MD)
 * [Deplux NAZE](./../NAZE/README.MD)

### 문법
`config.json`은 Deplux 호스팅을 더욱 더 전문적으로 활용할 수 있도록 해주는 설정 파일입니다.   
아래와 같이 사용할 수 있습니다 :
```json
{
    "git":{
        "repo":"https://github.com/Deplux/Document.git"
    }   
}
```
#### config.json의 요소
 * git : Git Repository 정보를 입력하여 봇에서 원클릭 Deploy를 할 수 있습니다.
    * repo : Git Repository의 주소

### 따라해보기
#### Git Repository로 Deploy하기
 1. config.json을 Deploy할 디렉터리 최상단에 위치시킵니다.
 2. Deploy할 디렉터리를 .zip 형식으로 압축시킨 뒤, .zip 파일을 업로드합니다.
 3. `!hosting` 명령어를 입력합니다.
 4. .zip을 업로드한 호스팅을 선택하고 `Github로 업로드하기`를 선택합니다.
 5. 자동으로 Deploy가 완료됩니다.

### 추가될 기능
 * git
    * Github Deploy Key 지원
 * 기타
    * todo