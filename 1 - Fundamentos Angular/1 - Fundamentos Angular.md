# ANGULAR NOTES

## DECORATOR

@NgModule

### @Input e @Output

[@Input e @Output link](https://angular.io/guide/inputs-outputs)

## EVENT BIND

### FORM

#### TEMPLATE DRIVEN

```typescript
export class MinhaClasseComponent {

  value: number;
  value2: number;

  method() {
    // Form logic
  }
}
```

```html
<form class="form" (ngSubmit)="method()">
  <!-- TWO-WAY EXAMPLE -->
  <input class="input" type="text" [(ngModel)]="value" name="value" />
  <!-- PROPERTY EXAMPLE -->
  <input class="input" type="text" [ngModel]="value2" name="value2" />
</form>
```

>OBS: [ngModelOptions]="{standalone: true}" utiliza-se em campos que não serão atualizados ou adicionar o name no campo, para que sofra todas as atualizações e validações

#### TWO-WAY BINDING

COMPONENTE -> TEMPLATE  
COMPONENTE <- TEMPLATE

#### PROPERTY BIND

COMPONENT -> TEMPLATE  
Mas se houver alteração no template, não é refletido no componente

## MOCK API

```bash
npm install -g json-server
```

>DICA: jsontots.com

## ROUTER

Exemplo de injetar uma classe quando a rota ativa e redirecionar o user:

```html
<a routerLink="/user/bob" routerLinkActive="class1 class2">Bob</a>
<a routerLink="/user/bob" [routerLinkActive]="['class1', 'class2']">Bob</a>
```

### GUARDA DE ROTA

`ng g guard dir/guard_name`

### ACTIVATED ROUTE

recebe o parametro (ID) para fazer uma busca parametrizada.

Ex:

Home com uma lista de gatos ->  
clique no gato de ID - 6 ->  
A tela de detalhe do gato recebe id 6 atraves do `activatedToute.snapshot.params.{ID}`  
Com o revebimento do ID, é só chamar o service

## INTERCEPTOR

`ng g interceptor dir/interceptor_name`

Intercepta toda req HTTP, que sai do front antes de bater no server
Ele é imutavel, sendo necessário deve ser clonado para manipular o atributo

## RESOLVER

`ng g resolver dir/resolver_name`

Busca uma informação no server, antes de o componente ser montado. Assim, evitando que o template apareça sem a informação carregada (em branco)

## VINCULAR ESTILOS

Em `angular.json` sob `build -> options -> styles` é declarado os arquivos que a aplicação vai utilizar

## ANGULAR CLI

ng generate module home --routing = Cria o modulo com arquivo de rota.

ng g c home/login = Cria um componente dentro do folder home

## HTTP CLIENT

Observable -> e como uma promisse que retorna o objeto da requisição.

HttpHeaders -> Classe que auxilia o envio de cabeçalho. Ex: token, Content-type.

## ENVIROMENTS

a `const enviroment` deve ter os mesmos atributos seja dev, prod ou outro stage

## COMPONENT

o ngConponent funciona como o `children` do React.js

### COMPOSIÇÃO

Assim como em aplicações React, utilizar o `component composition` para componentes maiores incorporar menores.

## COMPILADOR

A partir da versão 10 o Angular usa o `Ivy compiler`

## DEPLOY PROD

### SERVER

`npm i -g http-server`

### BUILD

`ng build --prod` sendo gerado o folder `dist`

### SERVER UP

`http-server .` em caso de estar dentro da pasta
