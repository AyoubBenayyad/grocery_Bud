let submit=document.querySelector("#submit");
let food=document.querySelector("#food");
let msg=Array.from(document.querySelectorAll(".msg"));
let list=document.getElementById("list");
let bud=[];
submit.addEventListener("click",add);
function add(){
    if(food.value==""){   
        msg.forEach(element => {
            element.style.display="none";
        });    
        msg[2].style.display="grid";
        msg[2].style.visibility="visible";
        setTimeout(()=> {msg[2].style.visibility="hidden";},2000);
    }
    else{
        bud.push(food.value);
        msg.forEach(element => {
            element.style.display="none";
        });
        msg[0].style.display="grid";
        msg[0].style.visibility="visible";
        setTimeout(()=> {msg[0].style.visibility="hidden";},2000);
        console.log(bud);
        const new_item = document.createElement('li');
        new_item.textContent=food.value;
        new_item.className = 'item';
        list.appendChild(new_item);
    }
}