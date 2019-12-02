# test_1
JavaScript test meta

1. Составьте программу, которая проверяет корректность баланса скобок в арифметическом выражении, т.е. что скобки установлены верно и правильно их вхождение, то есть если скобки так расположены [({})] , то это правильное вхождение, а вот [([) - неверное. Входной параметр - Строка - арифметическое выражение; Выходной параметр - "Верно";"Не верно". Использовать встроенные методы нельзя, функцию eval использовать нельзя.

Ответ


let isParenthesisMatching = (str) => {
    let stack = [];

    let open = {
        '{': '}',
        '[': ']',
        '(': ')'
    };

    let closed = {
        '}': true,
        ']': true,
        ')': true
    }

    for (let i = 0; i < str.length; i++) {

        let char = str[i];

        if (open[char]) {
            stack.push(char);
        } else if (closed[char]) {
            if (open[stack.pop()] !== char) return false;
        }
    }
    return stack.length === 0;
}

console.log(isParenthesisMatching('[['));



2. Напишите запрос, отыскивающий неуникальные значения id в таблице CREATE TABLE (id int not null, name text);

Ответ
CREATE TABLE test2 (
   id INTEGER not null,
   name TEXT
   
 );
 
 INSERT INTO test2 (id, name)
 values (1, 'Alex');
 
 INSERT INTO test2 (id, name)
 values (2, 'Ion');
 
 INSERT INTO test2 (id, name) 
 VALUES (2, 'Ion'); 

 INSERT INTO test2 (id, name) 
 VALUES (4, 'Lena');

 INSERT INTO test2 (id, name) 
 VALUES (4, 'Lena');

 select *
 from test2
 Group BY id
 HAVING COUNT(*)>1
 ;




