<h1 align="center">👋 Olá! Eu sou o Gusz</h1>

<p align="center">

---

  🚀 Sobre mim:
🎓 Estudante de Sistemas de Informação <br>
💻 Focado em Desenvolvimento Full Stack <br>
- 📍 Vitória da Conquista - BA, Brasil
---

  🛠️ Tecnologias e Ferramentas que estou estudando:

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)

---

  📂 Meus Projetos Recentes:

- ✅ [Projeto 1 - Academia-Em-Casa](https://github.com/guuszz/Academia-Em-Casa)
- ✅ [Projeto 2 - Gfocus-Lista-De-Tarefas](https://github.com/guuszz/Gfocus)
- ✅ [Projeto 3 - OFICINA-API](https://github.com/guuszz/OFICINA)


---

### 📈 Estatísticas do GitHub:

<div align="center">
  <img height="150em" src="https://github-readme-stats.vercel.app/api?username=guuszz&show_icons=true&theme=radical" />
  <img height="150em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=guuszz&layout=compact&theme=radical" />
</div>

---


-- Criação das tabelas
CREATE TABLE Passageiro (
    id_passageiro INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE Aeroporto (
    id_aeroporto INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    cidade VARCHAR(100) NOT NULL,
    estado CHAR(2) NOT NULL
);

CREATE TABLE Voo (
    id_voo INT PRIMARY KEY AUTO_INCREMENT,
    codigo_voo VARCHAR(10) UNIQUE NOT NULL
);

CREATE TABLE Trecho (
    id_trecho INT PRIMARY KEY AUTO_INCREMENT,
    id_voo INT NOT NULL,
    aeroporto_origem INT NOT NULL,
    aeroporto_destino INT NOT NULL,
    FOREIGN KEY (id_voo) REFERENCES Voo(id_voo),
    FOREIGN KEY (aeroporto_origem) REFERENCES Aeroporto(id_aeroporto),
    FOREIGN KEY (aeroporto_destino) REFERENCES Aeroporto(id_aeroporto)
);

CREATE TABLE Reserva (
    id_reserva INT PRIMARY KEY AUTO_INCREMENT,
    id_passageiro INT NOT NULL,
    FOREIGN KEY (id_passageiro) REFERENCES Passageiro(id_passageiro)
);

CREATE TABLE Reserva_Trecho (
    id_reserva INT NOT NULL,
    id_trecho INT NOT NULL,
    classe VARCHAR(20) NOT NULL,
    data_hora DATETIME NOT NULL,
    PRIMARY KEY (id_reserva, id_trecho),
    FOREIGN KEY (id_reserva) REFERENCES Reserva(id_reserva),
    FOREIGN KEY (id_trecho) REFERENCES Trecho(id_trecho)
);



