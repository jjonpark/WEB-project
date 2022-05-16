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
for(let i =0; i<10; i++) {
    console.log(i);
}

//배열을 반복문을 통해 출력하기 
const names=['멍멍이', '야옹이', '멍뭉이'];
for (let i =0 ; i<names.length; i++) {
    console.log(names[i])
}
```