---
layout: default
title: ReactJs
nav_order: 5
has_children: true
permalink: docs/reactjs
---

# O React.Js

O React.Js é uma biblioteca JS para criação de interfaces de usuário. Foi criada em 2011 pelo time do Facebook.
Hoje é a biblioteca mais utilizada para front-end com javascript, seguida do Angular e depois Vue.js.

## Iniciando um projeto novo

```
npx create-react-app my-app --template typescript
```

## Estilizando com CSS ou Sass

Você pode adicionar um arquivo css importando para a aplicação com:

```
import './styles.css'
```

Mas isso faz com que esse arquivo de estilo fique acessível globalmente, para que ele seja acessado apenas por um componente, é necessário utilizar a ideia de módulos, veja como instalar o plugin para [typescript](https://www.npmjs.com/package/typescript-plugin-css-modules).

```
npm i typescript-plugin-css-modules

// Depois adicione ao arquivo tsconfig.json
{
  "compilerOptions": {
    "plugins": [{ "name": "typescript-plugin-css-modules" }]
  }
}

// Agora utilize um import nomeado

import styles from 'styles.module.css';

const a = styles.myClass;
const b = styles['my_other-class'];
```

No import com modules, o react adiciona uma hash ao className no build, fazendo com que a classe seja sempre única.

```
<div class="container-diferente__Fh1cV">
```

## Props

Os props são informações passadas para o componentes. Se você criar um component `botão` por exemplo:

```
export default Input({type, placeholder}: {type: string, placeholder: string}){
    return (
        <input type={type} placeholder={placeholder} />
    )
}

.... No App
<Input type='number' placeholder='1200'>

```

O comando `children` serve para que o componente aceite algo escrito entre as tags de sua chamada.

```
<Button>ALGO AQUI</Button>

export default Button(){
    return (
        <button className="btn">{children}</button>
    )
}

```

## Estados

Para atualizar uma lista, adicionar dados, etc. É preciso utilizar estados, criando uma variável com colchetes e `useState`.

```
const [tarefas, setTarefas] = useState([{
    tarefa: 'React',
    tempo: '02:00:00'
}]);

return(
    <div>
        <button onClick={()=>{setTarefas = [...tarefas, {tarefa: 'nova', tempo: '05:00:00'}]}}>
        <ul>
            {tarefas.map((item, index) => {
                <li>{item.tarefa}</li>
                <li>{item.tempo}</li>
            })}
        </ul>
    </div>
)
```