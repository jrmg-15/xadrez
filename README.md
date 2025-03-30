!DOCTYPE html 

html lang=pt 

head 

    meta charset=UTF-8 

    meta name=viewport content=width=device-width, initial-scale=1.0 

    titleXadrez para Criançastitle 

    link rel=stylesheet href=httpscdnjs.cloudflare.comajaxlibschessboard-js1.0.0chessboard.min.css 

    script src=httpscdnjs.cloudflare.comajaxlibschess.js0.10.2chess.min.jsscript 

    script src=httpscdnjs.cloudflare.comajaxlibschessboard-js1.0.0chessboard.min.jsscript 

    style 

        body { 

            text-align center; 

            font-family Arial, sans-serif; 

        } 

        #board { 

            width 400px; 

            margin auto; 

        } 

        button { 

            margin-top 10px; 

            padding 10px; 

            font-size 16px; 

        } 

        #hint { 

            margin-top 10px; 

            font-size 18px; 

            color blue; 

        } 

        #ranking { 

            margin-top 20px; 

            font-size 18px; 

            color green; 

        } 

    style 

head 

body 

    h1Xadrez para Criançash1 

    div id=boarddiv 

    button onclick=resetGame()Reiniciar Jogobutton 

    button onclick=showHint()Dica de Movimentobutton 

    p id=hintClique em Dica de Movimento para sugestões!p 

    h2Rankingh2 

    ul id=rankingul 

     

    script 

        var board; 

        var game = new Chess(); 

        var ranking = JSON.parse(localStorage.getItem(ranking))  {}; 

  

        function onDragStart(source, piece) { 

            if (game.game_over()) return false; 

            if ((game.turn() === 'w' && piece.search(^b) !== -1)  

                (game.turn() === 'b' && piece.search(^w) !== -1)) { 

                return false; 

            } 

        } 

  
