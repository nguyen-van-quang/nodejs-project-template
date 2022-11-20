# nodejs-project-template
This is template a configuration for the NodeJs projects

## The packages to use on this projects:

1. [eslint](https://eslint.org/)
    ```bash
        npm init @eslint/config
    ```
2. [prettier](https://prettier.io/)
    ```
        npm i -D prettier eslint-plugin-prettier eslint-config-prettier
    ```
3. [airbnb](https://www.npmjs.com/package/eslint-config-airbnb-base)
    ```bash
        npm i -D airbnb eslint-config-airbnb-base eslint-config-airbnb-typescript
    ```
4. [commit lint](https://www.npmjs.com/package/@commitlint/config-conventional)
    ```bash
        npm install --save-dev @commitlint/config-conventional @commitlint/cli
        echo "module.exports = {extends: ['@commitlint/config-conventional']};" > commitlint.config.js
    ```
5. [lint-staged](https://github.com/okonet/lint-staged#Configuration)
    ```bash
        npm install --save-dev lint-staged
        echo "{\n  \"*\": \"prettier --write\",\n  \"*.ts\": \"eslint --fix\"\n}" > .lintstagedrc.json
    ```
6. [husky](https://github.com/typicode/husky)
    ```bash
        npm i -D husky
        npm pkg set scripts.prepare="husky install"
        npm run prepare
        npx husky add .husky/pre-commit "npm run prettier"
        npx husky add .husky/pre-commit "npm run lint"
        npx husky add .husky/pre-commit "npm run test"
        npx husky add .husky/commit-msg "npx --no -- commitlint --edit"
    ```


## Explain file package.json:

1. Script: **postinstall** will automatic run after npm install
    ```javascript
        {
            scripts: {
                ....
                "postinstall": "husky install"
            }
        }
    ```


