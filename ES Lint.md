# ES Lint

- 설치

  - ```
    npm init -y
    ```

  - ```
    npm install eslint --save-dev
    혹은
    npm i -D eslint
    ```

    - --save-dev 의미
      - package.json 파일의 devDependencies에 포함된다
      - 빌드시 해당 플러그인이 포함되지 않는다
        - eslint은 코드 분석도구이지 빌드될때 포함되야할 플러그인이 아니다

  - ```
    node_modules/.bin/eslint --init
    ```

  - 

- prettier와 통합하기

  - ```
    npm i -D prettier
    npm i -D eslint-config-prettier eslint-plugin-prettier
    ```

  - .eslintrc.js

    - ```javascript
      {
      	extends: ["plugin:prettier/recommend"]
      }
      ```

    - prettier로 검사

      - ```
        npx prettier "파일명.확장자"
        ```

      - 수정까지 하려면

        - ```
          npx prettier --write "파일명.확장자"
          ```

          

  - prettier는 vs code에서는 플러그인 설치로도 가능하다. 터미널에 커맨드를 통해 설치하고 세팅하지 않아도 사용할 수 있다.

- package.json

  - ```
    "scripts": {
    	"lint": "eslint ."
    }
    ```

  - ES Lint 실행

    - ```
      node_modules/.bin/eslint
      ```

    - 혹은

    - ```
      npm run lint
      ```

    - 수정까지 한번에 하고 싶다면

      - ```
        "scripts": {
        	"lint": "eslint .",
        	"lint:fix": "lint:fix": "eslint --fix --ext .js,.jsx ."
        }
        ```

        - ```
          npm run lint:fix
          ```

        - 임의로 lint:fix로 지정한거라 꼭 이렇게 하지 않아도 되고, "lint"에  "lint:fix": "eslint --fix --ext .js,.jsx ."로 설정하면 npm run lint로 수정까지 한번에 된다.

참고

https://eslint.org/docs/user-guide/getting-started

https://ithub.tistory.com/165

https://www.daleseo.com/js-eslint/

https://www.daleseo.com/js-prettier/

