# TESTANDO UMA APLICAÇÃO ANGULAR

## JASMINE

Documentação: [https://jasmine.github.io/](https://jasmine.github.io/)

## KARMA

Documentação: [https://karma-runner.github.io/latest/index.html](https://karma-runner.github.io/latest/index.html)

## UNIQUE ID

Criar uma classe que de um ID unico.

```markdown
|   ├── app
|     ├── shared
|       ├── services
|         ├── unique-id
|           └── unique-id.service.ts
```

## ESTRUTURA DE ESCRITA

```typescript

import { UniqueIdService } from '../../unique-id-service'

// O UniqueIdService.name cria o vinculo com o nome da classe e
// caso necessário a alteração do nome, reflete no teste

describe(UniqueIdService.name, () => {
  // #nameOfClassOrFunctionToTest | descrição do que deve fazer
  it(`#${UniqueIdService.prototype.generateUniqueIdWithPrefix.name} should generate id when called with prefix`, () => {
    // logic
  })
})
```

## HTML - DATA TYPES

[Data types link](https://www.w3.org/TR/html4/types.html)

## TESTBED

Injeta módulos nos testes
