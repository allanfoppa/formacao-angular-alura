# ACESSIBILIDADE

## EXTENSIONS

> [Screen Reader](https://chrome.google.com/webstore/detail/screen-reader/kgejglhpjiefppelpmljglcjbhoiplfn)

## DATA BIND

```html
[attr.aria-checked]="value === options.YES"
```

## TABINDEX

Um atributo abindex com o valor de -1, faz com que o elemento não ganhe foco no tab

```html
[attr.tabindex]="value === options.NO ? 0 : -1"
```

## ARIA-DISABLED

```html
[attr.aria-disabeld]="form.invalid"
```

O atributo `disabled` não permite que o elemento ganhe foco pelo teclado, inclusive tornando-o indetectável por screen readers. Já o atributo `aria-disabled` serve para indicar que um elemento, por algum motivo específico, está desabilitado para screen readers, porém ainda acessível pelo teclado.

## ARIA INVALID

Indica para screen readers que o componente de entrada está inválido.

## ARIA LABEL

```html
[attr.aria-label]="Texto para o Screen Reader ler, pode colocar string template"
```

Em caso de esse atributo nao existir, ele vai ler o valor contido na tag

## ARIA LIVE

O Screen Reader lê toda vez que for atualizado

```html
aria-live="true"
```

## ARIA ATOMIC

O Screen Reader lê tudo o que quem na tag

```html
aria-atomic="true"
```

## ARIA DESCRIBEDBY

Faz o vinculo via id com outra(o) tag/elemento para o screen reader

```html
[attr.aria-describedby]="id"
```

## DIRETIVAS - KEYBOARD MANAGER

```bash
touch file-name.directive.ts
touch file-name.module.ts
```

```typescript
@HostListener('click', ['$event'])
public manageKeys(event : KeyboardEvent): void {
  switch (event.key) {
    case 'ArrowUp':
      console.log('UP')
      break;
    case 'ArrowRight':
      console.log('Right')
      break;
    case 'ArrowDown':
      console.log('Down')
      break;
    case 'ArrowLeft':
      console.log('Left')
      break;
  }
}
```

## ANIMATIONS

Tudo gira em torno da trigger.

Importar `trigger` from `@angular/animations`
