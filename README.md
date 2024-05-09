# Calculator-Project
Its contains HTML CSS and JS

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="icon" href="image source/calculator.png">
    <link rel="stylesheet" href="style.css">

</head>
<body>

    <div class="main-container">
        <div class="main-sub-container">
        <h3 id="Calc" class="Calc">Calc</h3>
        <input id="switch" class="switch" type="checkbox" checked="true">
    </div>
        <div class="display">

            <input id="display" class="inputFiled" type="text" name="display">
        </div>
        <div class="sub-container">
 
            <div>
                <input type="button" value="7" onclick="appendToDisplay('7')">
                <input type="button" value="8" onclick="appendToDisplay('8')">
                <input type="button" value="9" onclick="appendToDisplay('9')">
                <input type="button" class="del" value="DEL" onclick="deleteLastChar()">
            </div>
            <div>
                <input type="button" value="4" onclick="appendToDisplay('4')">
                <input type="button" value="5" onclick="appendToDisplay('5')">
                <input type="button" value="6" onclick="appendToDisplay('6')">
                <input type="button" value="+" onclick="appendToDisplay('+')">
            </div>
            <div>
                <input type="button" value="1" onclick="appendToDisplay('1')">
                <input type="button" value="2" onclick="appendToDisplay('2')">
                <input type="button" value="3" onclick="appendToDisplay('3')">
                <input type="button" value="−" onclick="appendToDisplay('-')">
            </div>
            <div>
                <input type="button" value="." onclick="appendToDisplay('.')">
                <input type="button" value="0" onclick="appendToDisplay('0')">
                <input type="button" value="/" onclick="appendToDisplay('/')">
                <input type="button" value="X" onclick="appendToDisplay('*')">
            </div>
            <div>
                <input type="button" class="reset" value="RESET" onclick="resetDisplay()">
                <input type="button" class="equal" value="=" onclick="calculate()">
            </div>
        </div>

//// CSS of 

body{
    margin: 0;
    padding: 0;
    font-family: sans-serif    ;
    background-color: #3B4664;
}

.main-container{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin-top: 60px;

}
.main-container .main-sub-container{
    display: flex;
    flex-direction: row;
}
.main-container .main-sub-container .Calc{
    font-weight: bold;
    color: #ffffff;
    font-size: 18px ;
}
.main-container .main-sub-container .switch{
    margin-left: 270px;
    margin-top: 17px;
}


.switch {
    position: relative;
    height: 1.5rem;
    width: 3rem;
    cursor: pointer;
    -webkit-appearance: none;
    border-radius: 9999px;
    background-color: rgba(100, 116, 139, 0.377);
    transition: all .3s ease;
  }
  
  .switch:checked {
    background-color: rgba(236, 72, 153, 1);
  }
  
  .switch::before {
    position: absolute;
    content: "";
    left: calc(1.5rem - 1.6rem);
    top: calc(1.5rem - 1.6rem);
    display: block;
    height: 1.6rem;
    width: 1.6rem;
    cursor: pointer;
    border: 1px solid rgba(100, 116, 139, 0.527);
    border-radius: 9999px;
    background-color: rgba(255, 255, 255, 1);
    box-shadow: 0 3px 10px rgba(100, 116, 139, 0.327);
    transition: all .3s ease;
  }
  
  .switch:hover::before {
    box-shadow: 0 0 0px 8px rgba(0, 0, 0, .15)
  }
  
  .switch:checked:hover::before {
    box-shadow: 0 0 0px 8px rgba(236, 72, 153, .15)
  }
  
  .switch:checked:before {
    transform: translateX(100%);
    border-color: rgba(236, 72, 153, 1);
  }


.main-container .sub-container{
    background-color: #262C42;
    padding: 20px;
    border-radius: 10px;
}

.main-container .sub-container .inputFiled{
 width: 280px;
}
.main-container .display {
    display: flex;
    justify-content: center;
    margin-bottom: 10px;


}
.main-container .display .inputFiled{
    width: 330px;
    height: 85px;
    text-align: right;
    outline: none;
    font-size: 45px;
    border-radius: 10px;
    border: none;
    color: white;
    background-color: #171F32;
    font-weight: bold;
    padding: 5px 21px;


}
.main-container .sub-container  input{
    outline: none;
    border:  none;
    width: 60px;
    height: 50px;
    border-radius: 10px;
    margin: 10px;
    color: #474B58;
    font-weight: bold;
    font-size: 20px;
    box-shadow: 0 0 10px rgba(255, 255, 234, 0.3);

}
.main-container .sub-container  .del{
    background-color: #65729A;
    color: white;
}

.main-container .sub-container  .reset{
    width: 145px;
    background-color: #65729A;
    color: white;
}
.main-container .sub-container  .equal{
    width: 145px;
    background-color: #D14031;
    color: white;
}
.main-container .sub-container .inputFiled{
    text-align: right;
}
.main-container .sub-container .display{
    margin-bottom: 20px;
}


     ///// JS of.... 

let appendToDisplay = (value) => {
    let valueInput = document.getElementById('display');
    valueInput.value += value  
    
    
 
 }
 
 let resetDisplay = () => {
     document.getElementById('display').value = '';
 }
 
 let calculate = () => {
     let equalValue = document.getElementById('display').value
     if (equalValue === '') {
         alert('Input Filed Is Empty')
     }else{
         try {
             document.getElementById('display').value = eval(equalValue)
         } catch (error) {
             document.getElementById('display').value = ''
             alert(`Wrong Input : ${equalValue}`)
     }
 }
 
 }
 
 let deleteLastChar = ()=>{
     let valeSlice= document.getElementById('display').value 
     document.getElementById('display').value  = valeSlice.toString().slice(0,-1)
 }
 
 let calc = document.getElementById('Calc');
let switchButton = document.getElementById('switch');

let isColor = true;

switchButton.addEventListener('click', () => {
    if (isColor) {
        document.body.style.backgroundColor = 'white';
        calc.style.color = 'black';
    } else {
        document.body.style.backgroundColor = '#3B4664'
        calc.style.color = 'white'
    }
    
    isColor =! isColor
});

    </div>

<script src="calculater.js"></script>
</body>
</html>
