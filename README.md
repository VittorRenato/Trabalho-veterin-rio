create database clinica_veterinaria;
use clinica_veterinaria;


CREATE TABLE pacientes (
    id_paciente INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    especie VARCHAR(50) NOT NULL,
	idade INT
);

INSERT INTO Pacientes (nome, especie, idade) VALUES 
('Renatto', 'Gato', 23),
SELECT * FROM Pacientes;

CREATE TABLE veterinarios (
    id_veterinario  INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    especialidade VARCHAR(50)
);
INSERT INTO Veterinarios (nome, especialidade) VALUES 
('Vittor', 'Caninos');

select * from veterinarios;

CREATE TABLE consultas (
    id_consulta INT AUTO_INCREMENT PRIMARY KEY,
    id_paciente  INT NOT NULL,
    id_veterinario INT NOT NULL,
    data_consulta DATE NOT NULL,
	custo DECIMAL(10,2),
    FOREIGN KEY (id_paciente) REFERENCES Pacientes(id_paciente),
    FOREIGN KEY (id_veterinario ) REFERENCES Veterinarios(id_veterinario)
);	

insert into consultas values(1, 1, 1, '2024-09-24', 130.00);
select * from consultas;
