# LABORATORIO 7 - Finalización CI/CD - Manejo de Data - ORM
## Integrantes
- Jessica Muñoz
- Ricardo Pulido
## USANDO SPRING DATA DESDE CERO
Se sigue el tutorial de spring y se crea la base de datos local. Se descarga la imagen de MySQL y se corre el contenedor.

![contenedor](https://user-images.githubusercontent.com/123814482/231289333-5a578214-2e8d-4b4d-8989-f3260188805f.jpg)

Ahora en DBeaver se crea una tabla de la base de datos con las columnas indicadas.

![tabla](https://user-images.githubusercontent.com/123814482/231289397-951c50aa-d616-469d-8e3e-69080e7b9637.jpg)

Luego para establecer la conexión entre nuestro proyecto de spring y nuestra base de datos. Para esto se modificó el archivo *pom* añadiendole la dependencia de mysql

 ```
        <dependency>
            <groupId>com.mysql</groupId>
            <artifactId>mysql-connector-j</artifactId>
            <version>8.0.32</version>
        </dependency>
```

Para configurar la conexión debemos modificar el *application.properties*

```
spring.datasource.url=jdbc:mysql://localhost:3306/sys
spring.datasource.username=root
spring.datasource.password=my-secret-pw
spring.jpa.hibernate.ddl-auto=create-drop
```
Por último en la clase *Employee* se completa el constructor y se crea un constructor vacío en caso de no recibir parámetros.

```
public Employee() {}

public Employee(String string, String string2, String string3, double d) {
        this.firstName = string;
        this.lastName = string2;
        this.role = string3;
        this.salary = d;
}
```

Al ejecutar la aplicación muestra la creación de los usuarios y las consultas sobre la base de datos sin ningún error. Por ende la conexión 
fue establecida correctamente.

![prueba](https://user-images.githubusercontent.com/123814482/231291655-4223812e-33b0-4dd5-93e7-027257328c88.jpg)


## BIBLIOGRAFÍA
* Chola, A. (27 de enero del 2022). Spring Boot MySQLj Integration: 6 Easy Steps. Recuperado de: https://hevodata.com/learn/spring-boot-mysql/#Steps_to_Integrate_MySQL_with_Spring_Boot
* MVNRepository. (18 de enero del 2023). MySQL Connector/J » 8.0.32. Recuperado de: https://mvnrepository.com/artifact/com.mysql/mysql-connector-j/8.0.32
