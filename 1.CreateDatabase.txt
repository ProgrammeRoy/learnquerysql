use [master]
go
create database ExerciseDB
go
use ExerciseDB
go 
CREATE TABLE Departamento (
DepartamentoId varchar (4) PRIMARY KEY,
NombreDto varchar (20) NOT NULL,
Ciudad varchar (15),
DirectorId int
);CREATE TABLE Empleado (
EmpleadoId int NOT NULL PRIMARY KEY Identity(1000,1),
Nombre VARCHAR( 30 ) NOT NULL ,
Sexo CHAR( 1 ) NOT NULL CHECK (Sexo IN ('F', 'M') ),
FecNacimiento DATE NOT NULL ,
FecRegistro DATE NOT NULL,
Salario FLOAT NOT NULL,
Comision FLOAT NOT NULL,
Cargo VARCHAR( 15 ) NOT NULL,
JefeId int null,
DepartamentoId VARCHAR( 4 ) NOT NULL,
-- Declaración de las llaves foráneas
CONSTRAINT FK_Empl FOREIGN KEY (JefeId) REFERENCES Empleado,
CONSTRAINT FK_Dpto FOREIGN KEY (DepartamentoId) REFERENCES Departamento
);