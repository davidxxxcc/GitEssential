# DOM: Document Object Model

### ![](/assets/js-6)Code demo:

* `querySelector` will select the first DOM.
* `Math.floor `will discard the decimal of number
* `innerHTML can define HTML while textContent can only define text inside HTML`

`var scores, roundScore, activePlayer, dice;`

`scores = [0,0];`

`roundScore = 0;`

`activePlayer = 1;`

`dice = Math.floor(Math.random()*6)+1;`

`document.querySelector('#current-' + activePlayer).innerHTML = '<em>' + dice + '</em>'; //setter`

`var x = document.querySelector('#score-0').textContent; //getter`

`document.querySelector('.dice').style.display = 'none'; //setting css`

