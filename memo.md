# WEB study memo
## 자바 스크립트 문법
### 1) if else if else
```js
const a = 1;
if (a + 1 === 2) {
  const a = 2;
  console.log("if문 안의 a값은" + a);
}
console.log("if 문 밖의 a값은" + a);
```

### 2) switch case
```js
const device='iphone';
switch(device){
    case 'iphone':
        console.log('아이폰!')
        break;
    case 'ipad':
        console.log('아이패드!')
        break;
    case 'galaxy note':
        console.log('갤럭시 노트!')
        break
    default:
        console.log('모르겠네요...')
}
```
### 3) 함수
* 파라미터를 통해 결과를 만들어 내는것
```js
function add(a,b){
    return a+b;
}
const sum = add(1,2):
console.log(sum);

function hello(name){
    console.log('Hello, '+ name + '!');
}
hello('')

//Template Literal
function hello(name){
    console.log('Hello ${name}!')
}
hello('velopert')

//연습
function getGrade(score){
    if (score === 100){
        return 'A+';
    } else if (score >=90){
        return 'A';
    } else if (score ===89){
        return 'B+';
    } else if (score >=80){
        return 'B';
    } else if (score === 79){
        return 'C+';
    } else if (score >=70){
        return 'C';
    } else if (score >=69){
        return 'D+';
    } else if (score >=60){
        return 'D';
    } else{
        return 'F';
    }
}
const grade = getGrade(100)
console.log(grade)

// 화살표 함수 
const add = (a,b) => {
    return a+b
}
const hello = (name) =>{
    console.log('Hello, ${name}!')
}
hello('Velopert')
const sum = add(1,2);
console.log(sun)
```

### 4) 객체
* 우리가 어떤 값을 선언할 떄, 하나의 값에 여러값을 넣을 수 있게 해준다. 
```js
const dogName = '멍멍이'
const dogAge = 2;

//객체 
const dog = {
    name: '멍멍이',
    age:2,
    cute : true,
}
console.log(dog.name)

const ironMan ={
    name : '토니 스타크'
    actor : '로버트 다우니 주니어'
    alias : '아이언맨' 
};

const captinAmerica ={
    name : '스티븐 로져스'
    actor : '크리스 에반스'
    alias : '캡틴 아메리카 ' 
}
function print(hero){
    const text='${hero.actor}의 역할을 한 배우의 이름은 ${hero.name}입니다.'
    console.log(text);
}
print(ironMan);
print(captinAmerica)

//객체 비구조화 
function print(hero){
    const {name, actor, alias}=hero;
    const text='${actor}의 역할을 한 배우의 이름은 ${name}입니다.'
    console.log(text);
}
//객체 안에 함수 넣기 
const dog = {
    name='멍멍이',
    sound='멍멍',
    say : function say(){
        console.log(this.sound);
    }
};
const cat = {
    name: '야옹이'
    sound: '야옹~'
}
cat.say=dog.say;
cat.sat(); //-> 결과물이 야옹~ this 는 함수내의 변수를 가져옴
dog.say();
```

### 5) Getter 와 Setter
* 특정 값을 바꾸려고 하거나, 특정 값을 조회하려고 할 떄, 우리가 원하는 코드를 실행 할 수 있다.
```js
const number={
    a:1;
    b:2;
    get sum(){
        console.log('sum 함수가 실행됩니다!')
        return this.a + this.b;
    }
};
console.log(numbers);
console.log(numbers.sum); // sum()하지 않고 조회만 했는데, 실행이 댐

const dog ={
    _name:'멍멍이',
    set name(value){
        console.log('이름이 바뀝니다..'+value);
        this._name =value;
    }
};
console.log(dog._name); 
dog.name='뭉뭉이';
console.log(dog._name)

//연습
const number={
    _a:1,
    _b:2,
    sum:3,
    calculate(){
        console.log('calculate');
        this.sum = this._a +this._b;
    },
    get a(){
        return this._a;
    }
    get b(){
        return this._b;
    }
    set a(value){
        this._a=value;
        this.calculate();
    }
    set b(value){
        this._b=value;
        this.calculate();
    }
};
console.log(number.sum);
numbers.a=5;
numbers.b=7;
numbers.a=9;
```
### 6) 배열
* 자바스크립트에서 배열안의 객체는 모두 같은 스타일 일 필요는 없다. 
```js
const array=[1,2,3,4,5]
console.log(array);

const objects=[
    { name: '멍멍이' }.
    { name: '냐옹이' }.
];
console.log(obhects);
console.log(obhects[0]);
console.log(obhects[1]);

//배열에 새로운 항목 추가하기 
objects.push({
    name:'멍뭉이'
});

//배열의 크기를 알아내는법
console.log(objects.length);
```

### 5) 반복문
* 특정 작업을 반복적으로 할 때 사용
```js
//for 문
for(let i =0; i<10; i++) {
    console.log(i);
}

//배열을 반복문을 통해 출력하기 
const names=['멍멍이', '야옹이', '멍뭉이'];
for (let i =0 ; i<names.length; i++) {
    console.log(names[i])
}

//while 문
let i =0;
while (i<10){
    console.log(i);
    i++;
}

//for문 응용
const numbers=[10,20,30,40,50]
for(let number of numbers) {
    console.log(number);
}

const doogy={
    name: '멍멍이',
    sound: '멍멍',
    age:2
};
console.log(Object.entries(doggy));
console.log(Object.keys(doggy));
console.log(Object.values(doggy));

for (let key in doggy){
    console.log('${key}');
}

//연습 문제 배열은 받아서 더하게 하는 함수 만들기 
function sum0f(numbers){
    let num=0
    for (let i=0; i<numbers.length; i++){
        num+=numbers[i]
    }
    return num
}
const result=sum0f([0,1,2,3,4,5]);
console.log(result);

//퀴즈 
function biggerThanThree(numbers){
  let num=[]
   for (let i=0; i<numbers.length; i++){
       if (numbers[i]>3) {
           num.push(numbers[i])
       }
   }
   return num
}
const numbers=[1,2,3,4,5,6,7];
console.log(biggerThanThree(numbers))
```
### 6) 배열 내장함수
#### (1) forEach
```js
const superheroes = ['아이언맨', '캡틴 아메리카', '토르', '닥터스트레인지']

function print(hero){
    console.log(hero);
}

superheroes.forEach(print)
//이렇게 모든 내용을 표현 하거나 
superheroes.forEach(hero => {
    console.log(hero);
});
```

#### (2) map
* 배열내의 값을 바꾸고 싶을때, 사용
```js
const array = [1,2,3,4,5,6,7,8];

const squared=[];
for (let i; i<array.length; i++) {
    squared.push(array[i]*array[i]);
}
console.log(squared);

const square = n => n * n;
const squared = array.map(square);
or
const squared = array.map(n=>n*n);
console.log(squared)

const items=[
    {
        id:1,
        text:'hello'
    },
    {
        id:2,
        text:'bye'
    }
];
// 위 아이템에서 text 만 골라 내고 싶을때, 
const texts = items.map(item=> item.text);
console.log(texts);

const superheroes = ['아이언맨', '캡틴 아메리카', '토르', '닥터스트레인지']
//토르가 몇번째 있는지 알고 싶을떄, 
const index = superheroes.indexOf('토르'); //O는 대문자 o
console.log(index); --> 2가 나옴

const todos = [
    {
        id:1,
        text: '자바스크립트 입문',
        done:true,
    },
    {
        id:2;
        text:'함수 배우기'.
        done:true,
    },
    {
        id:3,
        text:'객체와 배열 배우기',
        done:true,
    },
    {
        id:4,
        text:'배열 내장 함수 배우기',
        done:false,
    }
]
//id 가 3인걸 찾고 싶을때, 
const index = todos.findIndex(todo =>todo.id ===3);
console.log(index)
//done 이 false 인걸 찾고 싶을떄 
const todo = todos.find(todo => todo.done ===false);
console.log(todo)
```

#### (3) filter
* 특정 요소로 필터링 하고 싶다. 
```js
const todos = [
    {
        id:1,
        text: '자바스크립트 입문',
        done:true,
    },
    {
        id:2;
        text:'함수 배우기'.
        done:true,
    },
    {
        id:3,
        text:'객체와 배열 배우기',
        done:true,
    },
    {
        id:4,
        text:'배열 내장 함수 배우기',
        done:false,
    }
]

const tasksNotDone = todos.filter(todo => todo.done === true);
consle.log(tasksNotDone)
```
#### (4) splice 와 slice
* 배열에서 특정 항목을 제거할 때, 사용 
```js
//splice 는 기존의 배열이 삭제가 된다. 
const numbers = [10,20,30,40];
const index = numbers.indexOf(30);
const spliced = numbers.splice(index,2) //index 부터 시작해서 2개 지우겠다. 
console.log(spliced);
console.log(numbers);

//slice 는 기존의 배열은 삭제가 되지 않음
const numbers = [10,20,30,40];
const sliced = numbers.slice(0,2) //0부터 시작 해서 2직전까지 선택
console.log(sliced);
console.log(numbers);

```

#### (5) shift, pop, unshift, push
```js
//shift 는 기존의 배열을 수정하게 된다.(맨 앞의 원소)
const numbers=[10,20,30,40];
const value = numbers.shift();
console.log(value);

//pop 는 기존의 배열을 수정하게 된다.(맨 뒤의 원소)
const numbers=[10,20,30,40];
const value = numbers.pop();
console.log(value);

//unshift는 맨 앞부분에 값을 추가하는것. 
const numbers=[10,20,30,40];
numbers.unshift(50);

//push 는 맨 뒷부분에 값을 추가해주는것. 
const numbers=[10,20,30,40];
numbers.push(50);

//conat 은 기존의 배열을 수정하지 않고 새로운 배열을 닮을 떄, 사용
const arr1 = [1,2,3];
const arr2 = [4,5,6];

const concated = arr1.concat(arr2);
console.log(arr1)
console.log(arr2)
console.log(concated)

//join은 배열내의 것을 합쳐서 문자열로 만들어 줄 떄, 사용
const array = [1,2,3,4,5];
console.log(array.join());
```

#### (6) reduce
* 배열이 주어졌을때, 배열의 값을 모두 사용하여 연산해야 할 떄, 사용
```js
const numbers =[1,2,3,4,5];
const num = numbers.reduce((accumulator, current) => accumulator + current, 0);
```
#### (7) QUIZ
```js
function countBiggerThanTen(numbers) {
  /* 구현해보세요 */
  let count = 0;
  numbers.forEach(n => {
    if (n > 10) {
      count++;
    }
  });
  return count;
}

const count = countBiggerThanTen([1, 2, 3, 5, 10, 20, 30, 40, 50, 60]);
console.log(count); // 5
```
### 7) 객체와 생성자 
* 함수를 통해서 새로운 객체를 만들고, 넣고 싶은 값 또는 함수를 넣을수 있게함 
```js
function Animal(type, name, sound) {
    this.type = type;
    this.name = name;
    this.sound = sound;
    // this.say = function() {
    //     consol.log(this.sound);
    // }
}
//프로토타입의 목적은 객체들끼리 공유할수 있는 어떠한 값이나 함수에다가 설정해주는?개념
Animal.prototype.say=function(){
    console.log(this.sound);
}
const dog = new Animal('개', '멍멍이', '멍멍');
const cat = new Animal('고양이', '야옹이', '야옹');

dog.say();
cat.say();

//class 를 이용해서 작성해보자 
class Animal {
    constructor(type,name,sound){
        this.tyep=type;
        this.name=name;
        this.sound=sound;
    }
    say() {
        console.log(this.sound);
    }
}

const dog = new Animal('개', '멍멍이', '멍멍');
const cat = new Animal('고양이', '야옹이', '야옹');

dog.say();
cat.say();

```
## function 복습
```js
function person(name, age) {
    console.log(this)
    this.name = name;
    this.age = age;
}

const p = new person('Mark', 37);
console.log(p,p.name,p.age);
//이렇게 생성이 가능한데 
//arrow function 의 경우에는
const Cat = (name, age ) => {
    this.name = name;
    this.age = age;
}
const c = new Cat('냥이', 1); //이렇게 작성할 경우 에러가 남

//함수안에서 함수를 만들어서 리턴
function plus(base){
    return function(num) {
        return base + num;
    }
}
const plus5 = plus(5);
console.log(plust5(10));

const plus7 = plus(7);
console.log(plus7(10));

//함수를 인자로 하여 함수를 호출
function heㅣlo(c) {
    console.log('hello');
    c();
}
hello(function()) {
    console.log('콜백');
}