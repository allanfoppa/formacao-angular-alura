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

## DIRETIVA CUSTOMIZADA (appAction)

```markdown
|   ├── app
|     ├── shared
|       ├── directives
|         ├── action
|           └── action.module.ts
|           └── action.directive.ts
```

```typescript
// action.module.ts
import { CommonModule } from '@angular/common';
import { NgModule } from '@angular/core';

import { ActionDirective } from './action.directive';

@NgModule({
  declarations: [ActionDirective],
  imports: [CommonModule],
  exports: [ActionDirective]
})
export class ActionDirectiveModule {}
```

```typescript
// action.directive.ts
import { Directive, EventEmitter, HostListener, Output } from '@angular/core';

@Directive({
  selector: '[appAction]'
})
export class ActionDirective {
  @Output() public appAction: EventEmitter<Event> = new EventEmitter();

  @HostListener('click', ['$event'])
  public handleClick(event: Event): void {
    this.appAction.emit(event);
  }

  @HostListener('keyup', ['$event'])
  public handleKeyUp(event: KeyboardEvent): void {
    this.appAction.emit(event);
  }
}
```

```html
<div class="like-widget-container"
  (appAction)="like()">
  <fa-icon
    role="button"
    tabindex="0"
    [attr.aria-describedby]="id"
    size="1x"
    [icon]="fonts.faThumbsUp">
  </fa-icon>
  <span
    [attr.id]="id"
    [attr.aria-label]="likes + ': people liked'"
    class="like-counter"
    aria-live="true"
    aria-atomic="true">
    {{ likes }}
  </span>
</div>
```

## ngOnChanges

Deve-se chamar `ngOnChanges` programaticamente em seu código, porque ele não será chamado automaticamente em nossos testes.
