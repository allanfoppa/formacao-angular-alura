# Avançando com bibliotecas

## Ferramentas

[Cmder](https://cmder.net/)

## OBSERVABLES

### TAP

Utilizado para fazer o debugger do serviço

```typescript
tap((values) => console.log('[values on tap]', values))
```

### PLUCK

Extraí de uma propriedade (objeto) o valor a ser iterado pelo `map`

```typescript
pluck('payload')
```

### MAP

Retorna um objeto para iterar

### SWITCH MAP

- Responsavel por uma alteração no fluxo, seja para filtrar informações ou alguma modificação desejada.
- O operador switchMap tem o papel de manipular o fluxo dos dados, e não o resultado

### MERGE

Faz o merge de um ou mais observables (utilizado para o carregamento inicial + filtro pelo input no curso)

### ASYNC MAP

```html
<div class="td-page-wrapper" *ngIf="acoes$ | async as acoes; else elseBlock">
  <div class="po-row">
    <div class="po-md-4" *ngFor="let acao of acoes">
      <app-card-acoes [acao]="acao"></app-card-acoes>
    </div>
  </div>
</div>
<ng-template #elseBlock><p>Não Há dados</p></ng-template>
```

## EVENTOS DE INPUT

## HttpCliente

### HttpParams

```typescript
const params = value ? new HttpParams().append('param', value) : undefined
```

## DEBOUNCE TIME

Como mostrado no exemplo do curso, ele serve para aguardar um tempo pré definido em uma constante, que, após esse tempo continua o fluxo.

Ex: um input de busca sendo disparado a após o tempo estabelecido.

## DISTINCT UNTIL CHANGED

serve como um comparador de dados, sendo o valor do input igual ao anterior ele não requisita novamente o serviço.
