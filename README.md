# kauaa
function criaCartao (categoria, pergunta, resposta) {
    console.log(categoria, pergunta, resposta)
    let container = document.getElementById ('container')
    let cartao = document.createElement('article')
    cartao.  className = 'cartao'
    cartao.innerHTML = `
    <div class="cartao__conteudo">
                    <h3>${categoria}</h3>
                    <div class="cartao__conteudo__pergunta">
                        <p>${pergunta}</p>
                    </div>
                    <div class="cartao__conteudo__resposta">
                        <p>${resposta}</p>
                    </div>
                </div>
    `
    let respostaEstavisivel = false
    function viraCartao () {
        respostaEstavisivel = !respostaEstavisivel
        cartao.classList.toggle('active', respostaEstavisivel)
    
    }
    cartao.addEventListener('click', viraCartao)
    container.appendChild(cartao)
}
‎assets/img
Whitespace-only changes.
‎assets/style.css
+113
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,113 @@
:root {
    --text-color: #DBE4EF;
    --card-front-color: #0a2342;
    --card-back-color: #00F4BF;
}
body {
    background-color: grey;
    font-family: Bai Jamjuree;
}
#container {
    display: flex; 
    flex-wrap: wrap;
    justify-content: space-between;
    padding: 2rem;
    gap: 2rem;
}
.cartao {
    margin: 1rem 1rem;
    height: 20rem;
    flex-grow: 1;
    flex-basis: calc(33% - 6rem);
}
.cartao__conteudo {
    background-color: var(--card-front-color);
    text-align: center;
    /* background-color: aquamarine; */
    height: 100%;
    transform-style: preserve-3d;
    transition: transform 300ms ease-in-out;
}
.cartao__conteudo h3 {
    color: var(--text-color);
    border: 1px solid var(--text-color);
    text-align: left;
    padding: 0.5rem;
    position: absolute;
    margin: 0.6rem;
    border-radius: 0.6rem;
    font-size: 1vw;
    backface-visibility: hidden;
}
.cartao__conteudo p {
    margin-top: 1rem;
    padding: 2rem;
    margin-top: 4rem;
    font-size: 1.4vw;
}
.cartao__conteudo__pergunta p {
    color: var(--text-color);
    font-weight: 500;
}
.cartao__conteudo__resposta p {
    color: var(--card-back-color);
    font-weight: 700;
}
.cartao.active .cartao__conteudo {
    transform: rotateY(180deg);
}
.cartao__conteudo__pergunta,
.cartao__conteudo__resposta {
    backface-visibility: hidden;
    position: absolute;
    height: 100%;
    width: 100%;
    box-sizing: border-box;
}
.cartao__conteudo__resposta {
    transform: rotateY(180deg);
    background-color: rgba(0, 244, 191, 0.2);
    border: 4px solid var(--card-back-color)
}
footer { 
    background-color: black;
    color: white;
    position: fixed;
    bottom: 0;
    width: 100%;
    height: 4rem;
}
footer p {
    text-align: center;
    font-size: 1rem;
    margin-top: 1rem;
}
@media (max-width: 560px) {
    body {
        background: url('img/mobile.low-end');
    }
    .cartao {
        flex: 1 0 calc(100% - 1rem)
    }
    .cartao__conteudo h3 {
        font-size: 3vw;
    }
    .cartao__conteudo p {
        font-size: 3.8vw;
    }
}
‎index.html
+31
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,31 @@
<!DOCTYPE html>
