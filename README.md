# 💘 Lovemeter
Inspired by classic Flash games like the Love Calculator, Lovemeter is a website that calculates the compatibility percentage between two people. It was developed as a way to practice my JavaScript skills, particularly random number generation.

## ⚙️ Technologies Used
- **Languages**: HTML, CSS, JavaScript
- **Tools**: Git

## 🔧 How It Works
Once the calculate button is clicked, the JavaScript code generates a random number between 1 and 100. The button can only be clicked after the user has entered two names, which must be different from each other. The resulting percentage is displayed instantly, accompanied by a heart emoji representing how good the result is.

## ⚙️ Button Click Event

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
