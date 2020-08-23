const express = require('express');

const server = express();

server.use(express.json());

const cursos = ['Node js', 'javascript', 'React native'];

//middleware global
server.use((req, res, next) => {
    return next();
});

function checkCurso(req, res, next) {
    if (!req.body.name)
        return res.status(400).json({
            error: "nome do curso é obrigatório"
        });
}

server.get('/cursos', (req, res) => {
    return res.json(cursos);
});

server.get('/cursos/:index', (req, res) => {

    // const nome = req.query.nome; //query string 
    const {
        index
    } = req.params; //path params 

    return res.json(cursos[index]);
});

server.post('/cursos', checkCurso, (req, res) => {

    const {
        name
    } = req.body;
    cursos.push(name);

    return res.json(cursos);
});

server.put('/cursos/:index', checkCurso, (req, res) => {

    const {
        index
    } = req.params;

    const {
        name
    } = req.body;
    cursos.push(name);

    curso[index] = name;

    return res.json(cursos);
});

server.delete('/cursos/:index', (req, res) => {

    const {
        index
    } = req.params;

    cursos.splice(index, 1);

    return res.json(cursos);
});

server.listen(3000);