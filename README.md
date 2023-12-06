
# promise

### example with no promise
```javascript
function sserver() {
    const wakeUpTime = Date.now() + 1000; //서버에 데이터 요청만 하는데 걸리는 시간 
    while (Date.now() < wakeUpTime) {}
    return 'process B';
}




console.log('process A');
console.log(sserver());
console.log('porcess C');
```
### Example with promise
```javascript
function sserver() {
    const wakeUpTime = Date.now() + 10; //서버에 데이터 요청만 하는데 걸리는 시간 
    while (Date.now() < wakeUpTime) {}
    return 'process B';
}

//promise 설계
function job() {
  return new Promise ( (res, rej) => {
    // 시간이 걸리는 작업 
     let data = sserver();
     res(data);
   });
}



console.log('process A');
job().then( data => console.log(data) ); //서버에 데이터 요청 후 받아오면 화면에 출력하기 
console.log('porcess C');
```

## json-server
1. make directory
2. make db.json file
3. npm init
4. npm install json-server
5. terminal$json-server ./db.json --port 4000

