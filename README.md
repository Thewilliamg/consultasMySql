1. **Obtener todos los productos en stock:**

   sql
   select productName, quantityInStock from products;

2. **Lista de empleados que trabajan en una oficina específica (por ejemplo, '1'):**

   sql
   select firstName, lastName, officeCode from employees where officeCode='1';

3. **Detalles de un cliente específico (por ejemplo, customerNumber = 101):**

   sql
   select \* from customers where customerNumber=101;

4. **Listar todos los pagos realizados por un cliente específico (por ejemplo, customerNumber = 101):**

   sql
   select checkNumber,amount,customerNumber from payments where customerNumber=101;

5. **Obtener todos los pedidos con estado 'Shipped':**

   sql
   select orderNumber,status,customerNumber from orders where status='Shipped';

6. **Cantidad total de productos en stock:**

   sql
   select sum(quantityInStock) from products;

7. **Lista de todos los empleados con su jefe (si tienen):**

   sql
   select lastName,reportsTo from employees where reportsTo IS NOT NULL;

8. **Detalles de oficinas en un país específico (por ejemplo, 'USA'):**

   sql
   select officeCode,country from offices where country='USA';

9. **Listar todos los clientes en una ciudad específica (por ejemplo, 'Madrid'):**

   sql
   select customerName,city from customers where city='Madrid';

10. **Productos con precio de compra mayor a 50:**

    sql
    select productCode,productName,buyPrice from products where buyPrice>50;

### Consultas Multitabla

1. **Obtener todos los pedidos realizados por un cliente específico (por ejemplo, customerNumber = 101) con detalles del producto:**

   sql
   select o.customerNumber,o.orderNumber,o.orderDate,d.productCode,d.quantityOrdered,d.priceEach from orders o INNER JOIN orderdetails d USING(orderNumber) where customerNumber=101;

2. **Listar todos los empleados junto con la oficina en la que trabajan:**

   sql
   select e.employeeNumber,e.firstName,e.officeCode,o.city from employees e INNER JOIN offices o USING(officeCode);

3. **Listar todos los clientes junto con su representante de ventas:**

   sql
   select c.customerNumber,c.customerName,c.salesRepEmployeeNumber,e.firstName from customers c INNER JOIN employees e ON e.employeeNumber=c.salesRepEmployeeNumber WHERE salesRepEmployeeNumber IS NOT NULL;

4. **Obtener el nombre y la cantidad total ordenada de cada producto:**

   sql
   select productCode, productName, quantityInStock FROM products ORDER BY quantityInStock;

5. **Listar todas las oficinas y el número de empleados en cada una:**

   sql
   select officeCode,COUNT(officeCode) FROM employees GROUP BY officeCode;

6. **Obtener detalles de los pedidos, incluyendo la información del cliente y los productos ordenados:**

   ```sql
   
   ```

7. **Listar todos los pagos realizados, junto con la información del cliente y su representante de ventas:**

   ```sql
   
   ```

8. **Obtener una lista de todos los productos, junto con sus líneas de productos y el total de cantidad ordenada:**

   ```sql
   
   ```

9. **Listar todos los pedidos con detalles del cliente y el nombre del representante de ventas:**

   ```sql
   
   ```

10. **Obtener el total de pagos realizados por cada cliente y el nombre del representante de ventas asignado:**

   ```sql
   
   ```