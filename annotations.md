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