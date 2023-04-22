<template>
  <div id="tela">
        <header>
            <h1>Atendimento Online</h1>
        </header>
        <main id='conteudo'>
            <div class="atendente">
                <p><strong>Atendente diz:</strong></p>
                <div class="mensagematen">
                    <p>Boa Tarde, você está falando com a Juliana, gostariamos de saber sua opinião sobre a nossa marca.</p>
                </div>
            </div>
            <div class = "atendente">
                <p><strong>Atendente diz:</strong></p>
                <div class="mensagematen">
                    <p>De 0 à 10, qual a nota você da ao nosso atendimento.</p>
                </div>
            </div>
            <div class="usuario" v-show = "array.lenght != 0" v-for="(msg,index) in array" :key="index">
                <p><strong>Você diz:</strong></p>
                <div class="mensagemusua">
                    <p>{{msg}}</p>
                </div>
                    
            </div>
        
        </main>
        <section class="footer">
                <input id='campoDigitar' type="text" placeholder="Digite sua mensagem... " v-model = 'msg' />
                <button id='botao1' @click="enviarMensagem"><img src="./assets/icone-de-enviar.png" alt="icone de enviar"></button>   
        </section>
    </div>

</template>

<script>
    export default {
        name: 'app',
        data() {
            return {
                array: [],
                msg: ''
            }
        },
        methods: {
            enviarMensagem(){
                if (this.msg === ''){
                    return
                }
                this.array.push(this.msg)
                console.log(this.msg,this.array)
                this.msg = ''
            }
        }

    }





</script>

<style>

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}


body {
    height:100vh;
    justify-content: center;
    align-items: center;
    display:flex;
    font-family:'Josefin Sans', sans-serif;
    background-image: url(assets/fundo.jpg);
    color: white;
}

#tela {
    border-style: solid;
    border-radius: 25px;
    backdrop-filter: blur(15px);
    width: 500px;
    height: 800px;
    
}

header {
    font-size: 25px;
    justify-content: center;
    display: flex;
    padding-top: 10px;
    border-bottom-style: solid;
    border-radius: 25px;

}

div.atendente {
    padding: 20px 20px 20px;
    font-size: 30px;
    padding-top: 50px;
}

div.usuario {
    padding: 20px 20px;
    text-align:right;
    font-size: 30px;
    padding-top: 50px;
}


div.mensagematen {
    border : solid rgb(255, 255, 255);
    border-radius: 25px;
    border-width: 1px;
    padding: 15px 15px;
    font-size: 20px;
    margin-right:150px;
}


div.mensagemusua {
    border : solid rgb(255, 255, 255);
    border-radius: 25px;
    border-width: 1px;
    padding: 15px 15px;
    font-size: 20px;
    margin-left:150px;
}




section.footer {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 25px;
    padding: 15px;
    
    border-top: 3px solid white;
    border-radius: 25px;
}



button {
    background-color: transparent;
    font-weight: bold;
    color: white;
    border: 2px solid white;
    border-radius: 25px;
    padding: 5px;
    margin-left: 15px;
    margin-top: 5px;
    transition: 100ms linear;
    width: 60px;
}


button:active {
    background-color: rgb(255, 255, 255);
}

input {
    font-family: 'Josefin Sans', sans-serif;
    background-color: transparent;
    color: white;
    border: 2px solid white;
    border-radius: 25px;
    padding:0px 20px;
    margin-top: 5px;
    width: 350px;
    height:45px;
    font-size: 20px;
    
}

input::placeholder {
    color: rgb(255, 255, 255);
    opacity: 0.7;
    font-size: 20px;
    text-align:left;
    
  }


  img {
    width: 35px;
    height:35px;
    object-fit: contain;
    justify-content:center;
    align-items:center;
    
    
}

main {
overflow: auto;
height: 600px;
}



main::-webkit-scrollbar {
    width: 6px;
  }
  
   
  main::-webkit-scrollbar-track {
    background-color: transparent;
    border-radius: 5px;
    margin: 15px;
  }
  
  main::-webkit-scrollbar-thumb {
    background-color: #1f1f51;
    border-radius: 5px;
    margin: 15px;
  }
</style>
