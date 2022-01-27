# Postman
## Postman hw_2
### /first
1. Отправить запрос.
2. Статус код 200 </br>
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Проверить, что в body приходит правильный string</br>. 
```
pm.test("Body is correct", function () { 
pm.response.to.have.body("This is the first responce from server!");
});
```
_______________________

### /user_info_3 </br>
1. Отправить запрос.
2. Статус код 200
```
>pm.test("Status code is 200", function () {</br>
    pm.response.to.have.status(200);</br>
});
```

3. Спарсить response body в json. </br>
`var resp = pm.response.json();`

4. Проверить, что name в ответе равно name s request (name вбить руками.) </br>
`pm.test("The response name is equal to the request name", function() {
    pm.expect(resp.name).to.eql("Kate");
});`

5. Проверить, что age в ответе равно age s request (age вбить руками.) </br>
`pm.test("The response age is equal to the request age", function(){
    pm.expect(resp.age).to.eql('23');
});`

6. Проверить, что salary в ответе равно salary s request (salary вбить руками.) </br>
`pm.test("The response salary is equal to the request salary",function(){
    pm.expect(resp.salary).to.eql(1000);
});`

7. Спарсить request. </br>
`var req = request.data;`

8. Проверить, что name в ответе равно name s request (name забрать из request.) </br>
`pm.test("The response name is equal to the request name", function() {
    pm.expect(resp.name).to.eql(req.name);
});`

9. Проверить, что age в ответе равно age s request (age забрать из request.) </br>
`pm.test("The response age is equal to the request age", function(){
    pm.expect(resp.age).to.eql(req.age);
});`

10. Проверить, что salary в ответе равно salary s request (salary забрать из request.) </br>
`pm.test("The response salary is equal to the request salary",function(){pm.expect(resp.salary).to.eql(Number(req.salary));
});`

11. Вывести в консоль параметр family из response.</br>
`console.log(resp.family)`

12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)</br>
`pm.test("U_salary_1_5_year in the response is equal salary * 4 from the request", function(){
    pm.expect(resp.family.u_salary_1_5_year).to.eql(req.salary * 4)
});
`
_______________________

### /object_info_3
1. Отправить запрос.
2. Статус код 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

3. Спарсить response body в json.
var resp = pm.response.json();

4. Спарсить request.
var req = pm.request.url.query.toObject();

5. Проверить, что name в ответе равно name s request (name забрать из request.)
pm.test("The response name is equal to the request name", function(){
    pm.expect(resp.name).to.eql(req.name);
});

6. Проверить, что age в ответе равно age s request (age забрать из request.)
pm.test("The response age is equal to the request age", function(){
    pm.expect(resp.age).to.eql(req.age);
});

7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
pm.test("The response salary is equal to the request salary", function(){
    pm.expect(String(resp.salary)).to.eql(req.salary);
});

8. Вывести в консоль параметр family из response.
console.log(resp.family);

9. Проверить, что у параметра dog есть параметры name.
pm.test("The dog parameter has name",function(){
    pm.expect(resp.family.pets.dog).to.have.property('name');
});

10. Проверить, что у параметра dog есть параметры age.
pm.test("The dog parameter has age", function(){
    pm.expect(resp.family.pets.dog).to.have.property('age');
});

11. Проверить, что параметр name имеет значение Luky.
pm.test("The name parameter is equal Luky", function(){
    pm.expect(resp.family.pets.dog.name).to.eql('Luky');
});

12. Проверить, что параметр age имеет значение 4.
pm.test("The age parameter is equal 4", function(){
    pm.expect(resp.family.pets.dog.age).to.eql(4);
});

_______________________

### /object_info_4
1. Отправить запрос.
2. Статус код 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

3. Спарсить response body в json.
var resp = pm.response.json();

4. Спарсить request.
var req = pm.request.url.query.toObject();

5. Проверить, что name в ответе равно name s request (name забрать из request.)
pm.test("The name parameter response is equal to the request name", function(){
    pm.expect(resp.name).to.eql("Kate");
});

6. Проверить, что age в ответе равно age из request (age забрать из request.)
pm.test("The age parameter response is equal to the request age", function(){
    pm.expect(resp.age).to.eql(23);
});

7. Вывести в консоль параметр salary из request.
console.log(req.salary);

8. Вывести в консоль параметр salary из response.
console.log(resp.salary);

9. Вывести в консоль 0-й элемент параметра salary из response.
console.log(resp.salary[0]);

10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
console.log(resp.salary[1]);

11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
console.log(resp.salary[2]);

12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
pm.test("The salary[0] parameter is equal the salary from the request", function(){
    pm.expect(resp.salary[0]).to.eql(Number(req.salary));
});

13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
pm.test("The salary[1] = (salary from the request) * 2", function(){
    pm.expect(Number(resp.salary[1])).to.eql(req.salary * 2);
});

14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
pm.test("The salary[2] = (salary from the request) * 3", function(){
    pm.expect(Number(resp.salary[2])).to.eql(req.salary * 3);
});

15. Создать в окружении переменную name
16. Создать в окружении переменную age
17. Создать в окружении переменную salary

18. Передать в окружение переменную name
pm.environment.set("name", "Kate");

19. Передать в окружение переменную age
pm.environment.set("age", "23");

20. Передать в окружение переменную salary
pm.environment.set("salary", "1000");

21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
for(let i = 0; i < resp.length; i++){
    console.log(resp.salary[i]);
}

_______________________

### /user_info_2
1. Вставить параметр salary из окружения в request
2. Вставить параметр age из окружения в age
3. Вставить параметр name из окружения в name
4. Отправить запрос.
5. Статус код 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

6. Спарсить response body в json.
var resp = pm.response.json();

7. Спарсить request.
var req = request.data;

8. Проверить, что json response имеет параметр start_qa_salary
pm.test("The json parameter has the start_qa_salary", function(){
    pm.expect(resp).to.have.property("start_qa_salary");
});

9. Проверить, что json response имеет параметр qa_salary_after_6_months
pm.test("The json response from the response has the qa_salary_after_6_months", function(){
    pm.expect(resp).to.have.property("qa_salary_after_6_months");
});

10. Проверить, что json response имеет параметр qa_salary_after_12_months
pm.test("The json parameter from the response has the qa_salary_after_12_months", function(){
    pm.expect(resp).to.have.property("qa_salary_after_12_months");
});

11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
pm.test("The json parameter from the response has the qa_salary_after_1.5_year", function(){
    pm.expect(resp).to.have.property("qa_salary_after_1.5_year");
});

12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
pm.test("The json parameter from the response has the qa_salary_after_3.5_years", function(){
    pm.expect(resp).to.have.property("qa_salary_after_3.5_years");
});

13. Проверить, что json response имеет параметр person
pm.test("The json parameter from the response has the person parameter", function(){
    pm.expect(resp).to.have.property("person");
});

14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
pm.test("The start_qa_salary is equal the salary from the request", function(){
    pm.expect(resp.start_qa_salary).to.eql(Number(req.salary));
});

15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
pm.test("The qa_salary_after_6_months is equal (the salary from request) * 2", function(){
    pm.expect(resp.qa_salary_after_6_months).to.eql(Number(req.salary) * 2)
});

16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
pm.test("qa_salary_after_12_months is equal salary * 2.7 from request", function(){
    pm.expect(resp.qa_salary_after_12_months).to.eql(req.salary * 2.7);
});

17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
pm.test("qa_salary_after_1.5_year is equal salary * 3.3 from request", function(){
    pm.expect(resp['qa_salary_after_1.5_year']).to.eql((req.salary) * 3.3);
});

18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
pm.test("The qa_salary_after_3.5_years =  salary * 8 from the request", function(){
    pm.expect(resp['qa_salary_after_3.5_years']).to.eql(Number(req.salary) * 3.8)
});

19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
pm.test("In the person u_name[1] is equal salary from the request", function(){
    pm.expect(resp.person.u_name[1]).to.eql(Number(req.salary));
});

20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
pm.test("The u_age parameter is equal age from the request", function(){
    pm.expect(resp.person.u_age).to.eql(Number(req.age));
});

21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
pm.test("The u_salary_5_years parameter is equal salary * 4.2 from the request", function(){
    pm.expect(resp.person.u_salary_5_years).to.eql(Number(req.salary) * 4.2);
});

22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
for(var key in resp.person) {
   if(typeof(resp.person[key]) == 'object'){
       for(let i = 0; i < Object.keys(resp.person[key]).length; i++){
           console.log(resp.person[key][i]);
       }
   }
   else if(typeof(resp.person[key]) != 'object') {
        console.log(resp.person[key]);
   }
}
_______________________