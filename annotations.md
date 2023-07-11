package.json engines é possível setar a versao do node a ser utilizada:

```json
{
  "engines": {
    "node": "18.x"
  }
}
```

skipLibCheck, pula a validacao do typescript em bibliotecas dentro do node_modules, melhorando a performance do build

forceConsistentCasingInFileNames, determina que o import siga as regras de case name do nome do arquivo, evitando erros de build entre diferentes sistemas operacionais.

```
filename: controller.ts
```

```js
import * as controller from './Controller' // com o forceConsistentCasingInFileNames isto está errado.
import * as controller from './controller' // este será o correto.
```

Para habilitar a importação de uma pasta inteira, deve-se colocar no tsconfig o moduleResolution: node

ECMASCRIPT MODULES x COMMONJS
o commonjs transforma para require os imports do typescript (mais funcional)

caso for usar o ecmascript modules lembrar de colocar type: module no package.json

esModuleInterop - Resolve problema de imports/require/babbel entre as bibliotecas

```json
"baseUrl": "src",
"paths": {
  "@/*": ["*"],
  "@/tests/*": ["../tests/*"]
}
```

Paths sao alias para a urlBase, sempre bom usar o @ para isso.
Mas o commonjs Javascript nao sabe por isso usaremos uma biblioteca para isso: module-alias (@types/module-alias)
