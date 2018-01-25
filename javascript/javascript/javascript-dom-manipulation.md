# DOM: Document Object Model

![](/assets/js-6)Code demo:

`var scores, roundScore, activePlayer, dice;`

`scores = [0,0];`

`roundScore = 0;`

`activePlayer = 1;`

`dice = Math.floor(Math.random()*6)+1;`

`document.querySelector('#current-' + activePlayer).innerHTML = '<em>' + dice + '</em>'; //setter`

`var x = document.querySelector('#score-0').textContent; //getter`

`document.querySelector('.dice').style.display = 'none'; //setting css`

