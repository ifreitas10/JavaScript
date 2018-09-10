# Interagindo bolinha;

<canvas width="600" height="400"></canvas>

<script>

    var tela = document.querySelector('canvas');
    var pincel = tela.getContext('2d');
    pincel.fillStyle = 'lightgray';
    pincel.fillRect(0, 0, 600, 400);

    function desenhaCirculo(x, y, raio, cor) {

        pincel.fillStyle = cor;
        pincel.beginPath();
        pincel.arc(x, y, raio, 0, 2 * Math.PI);
        pincel.fill();
    }

    function limpaTela() {

        pincel.clearRect(0, 0, 600, 400);
    }

    //bolinha aumenta entre 20 e 30

    var x = 20;
    var sentido = 1;

    function bolinhaVaiVolta(){
        
        if(x > 600){
            sentido = -1;
        }else if(x < 0){
            sentido = 1;
        }

        x = x + sentido;    
    }

    var raio = 19;
    var tamanhoAceitavel = 1;

    function pulsaBola(){
        
        if(raio > 30){
            
            tamanhoAceitavel = -1;
        
        }else if(raio < 20){
            
            tamanhoAceitavel = 1;
        }

        raio = raio + tamanhoAceitavel;        
    }

    function movimentaBola(){
        
        bolinhaVaiVolta();
        limpaTela();
        desenhaCirculo(x, 40, raio, "lightblue");
        pulsaBola();
    }   


    setInterval(movimentaBola, 20);

</script>
