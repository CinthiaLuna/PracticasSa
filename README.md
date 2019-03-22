# PracticasSa
Practicas
De la cadena "Convirtiendo formato de cadena" hacer que se muestra la misma cadena con la primera letra de cada palabra en mayúsculas.
SELECT INITCAP('Convirtiendo formato de cadena') FROM dual;
• Obtenga la tercera ocurrencia de la letra a en la palabra “parangaricutirimicuaro”, comenzando en el segundo carácter:
SELECT INSTR ('parangaricutirimicuaro', 'a', 2, 2) FROM dual;
• Convierta a minúsculas la frase: “SI LLORAS POR HABER PERDIDO EL SOL LAS LÁGRIMAS NO TE PERMITIRÁN VER LAS ESTRELLAS.”
SELECT LOWER('SI LLORAS POR HABER PERDIDO EL SOL LAS LÁGRIMAS NO TE PERMITIRÁN VER LAS ESTRELLAS') FROM dual;
• Obtenga la frase “no hay nada que temer”, sin la palabra ‘no’
SELECT LTRIM('no hay nada que temer','no ') FROM dual;
• De la frase “La esperanza nunca muere”, cambie el ‘nunca’ por la cadena ‘No’:
SELECT REPLACE('La esperanza nunca muere','nunca', 'no') FROM dual;
• Obtenga el valor absoluto de los números -8473 y 39050:
SELECT ABS(-8473), ABS(39050) FROM dual;
• Obtenga el residuo de 23/1.7, 78/9 y -18/34:
SELECT MOD(23,1.7), MOD(78,9), MOD(-18,34) FROM dual;
• Obtenga el resultado de elevar 23 a la séptima potencia:
SELECT POWER(23,7) FROM dual;
• Trunque el número 9483.94932. 4 posiciones a la derecha del decimal, y 2 posiciones a la izquierda:
SELECT TRUNC(9483.94932,4), TRUNC(9483.94932,-2) FROM dual;
• Obtenga el último día del mes de la fecha actual.
SELECT LAST_DAY(CURRENT_DATE) FROM dual;
• Calcule cuántos meses existen entre el 2 de enero del 2012 y el 4 de junio del mismo año:
SELECT MONTHS_BETWEEN(TO_DATE('06-04-2002','MM-DD-YYYY'),
TO_DATE('01-02-2002','MM-DD-YYYY')) FROM dual;
• A partir de la fecha del sistema, calcule el siguiente martes:
SELECT NEXT_DAY(SYSDATE,'Tuesday') Proximo_Martes FROM dual;
• Convertir la cadena “1010” a número:
SELECT TO_NUMBER ('1010') FROM dual;
• De la tabla employees escribe una consulta que devuelva el salario del empleado con id=10, la salida debe tener el formato: “El salario de Juan Pérez es de:
CONCAT: SELECT CONCAT (CONCAT (CONCAT (CONCAT ( 'El usuario ',first_name),last_name),'Salario'), salary) FROM employees WHERE id = 10;
||: SELECT 'El usuario '|| first_name || ' ' || last_name || ' Salario ' || salary FROM employees
WHERE id = 10;
• Convertir la N en Ñ:
SELECT TRANSLATE('ñ','ñ', 'n') FROM dual;
• De la tabla employees escribe una consulta que devuelva el salario en el formato $9,999.99:
SELECT TO_CHAR(Salary, '$9G999D99')Salario FROM employees;
• Réstale a la fecha actual 3 meses:
SELECT sysdate - to_yminterval('00-03') FROM dual;
• Mostrar el promedio de del salario de la tabla employees agrupados por id:
SELECT id, AVG(Salary) Salario FROM employees GROUP BY id;
• Mostrar el promedio de todos los salarios diferentes en la tabla employees donde el salario sea mayor de 1300 y menor de 1500:
SELECT AVG(Salary) FROM employees where Salary > 1300 AND Salary < 1500;
• De la tabla de employees sumar los salarios por departamento y mostrar el total de empleados por departamento:
SELECT departament_id, SUM(salary), COUNT(departament_id) "Empleados" FROM employees GROUP BY departament_id;
• Mostrar id la suma de salarios de los empleados y el número de id distintos de la tabla de employees:
SELECT id, SUM(salary) FROM employees WHERE id NOT LIKE '%REP%' GROUP BY id HAVING SUM(salary) < 950 ORDER BY SUM(salary);
