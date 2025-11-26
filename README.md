# 💘 Lovemeter
Inspirado nos antigos jogos de flash de calculadora do amor, o loveômetro é um website que calcula a porcentagem de compatibilidade entre duas pessoas, feito com o intuito de treinar minhas habilidades em javascript e gerar números aleatórios. [Acesse aqui](https://mincostta.github.io/lovemeter/).

## ⚙️ Tecnologias Usadas
- **Linguagens**: HTML, CSS, Javascript
- **Ferramentas**: Git

## 🔧 Funcionamento
Assim que o botão de cálculo é acionado, o código em Javascript irá gerar um número aleatório entre 1 e 100. O botão só pode ser acionado após o usuário ter digitado dois nomes, com a condição de ambos não poderem ser iguais. A porcentagem prontamente é mostrada, acompanhada de um coração que represente o quão bom é aquele resultado.

## ⚙️ Evento de Clique no Botão

```javascript
    botao.addEventListener('click', ()=>{
    const pessoa1Input = document.getElementById('pessoa1');
    const pessoa2Input = document.getElementById('pessoa2');
    
    const pessoa1 = pessoa1Input.value;
    const pessoa2 = pessoa2Input.value;

    if (pessoa1.trim() == '' || pessoa2.trim() == '') {
        texto.innerText = "Digite os dois nomes necessários";
        resultado.style.display = 'none';
        coracao.src = './imgs/coração-inicial.png';
        botao.innerText = "Calcular";
    }

    else if (pessoa1 == pessoa2) {
        texto.innerText = "Os nomes não podem ser iguais";
        resultado.style.display = 'none';
        coracao.src = './imgs/coração-inicial.png';
        botao.innerText = "Calcular";
        pessoa1Input.value = '';
        pessoa2Input.value = '';
    }

    else {
        var porcentagem = Math.random();
        porcentagem = porcentagem * 100 + 1;
        porcentagem = Math.floor(porcentagem);

        const numero = porcentagem + "%";

        resultado.innerText = numero;
        resultado.style.display = 'block';

        texto.innerText = pessoa1 + " e " + pessoa2 + " têm " + porcentagem + "% de compatibilidade";

        pessoa1Input.value = '';
        pessoa2Input.value = '';

        if (porcentagem <= 25) {
            coracao.src = './imgs/coração-quebrado.png';
        }

        else if (porcentagem <= 40) {
            coracao.src = './imgs/coração-colado.png';
        }

        else if (porcentagem <= 60) {
            coracao.src = './imgs/coração-dois.png';
        }

        else if (porcentagem <= 80) {
            coracao.src = './imgs/coração-cheio.png';
        }

        else if (porcentagem <= 100) {
            coracao.src = './imgs/coração-anjo.png';
        }

        botao.innerText = "Refazer";
    }
});
```
