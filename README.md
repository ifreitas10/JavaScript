# JavaScript
//Desenhando dois esquadros

<canvas width="600" height="400"> </canvas>

<script> 
	//recebe o parâmetro da tela
	var tela = document.querySelector("canvas");
  
	//desenha na tela
	var pincel = tela.getContext("2d");

	//desenhar um esquadro
	function desenhaEsquadro(xa, ya, xc, yc, cor){
      pincel.fillStyle = cor;
      //iniciar o esquadro
      pincel.beginPath();
      
      //ponto 'A' do esquadro
      pincel.moveTo(xa, ya);
      
      //Reutilizo os parâmetros do ponto 'A' e 'C', pois o 'B' depende deles.
      pincel.lineTo(xa, yc);
      
      //ponto 'C' do esquadro
      pincel.lineTo(xc, yc);	
      
      //pintar o desenho	
      pincel.fill();
	}

	desenhaEsquadro(50, 50, 400, 400, "black");
	desenhaEsquadro(100, 175, 275, 350, "white");	
  
</script>
