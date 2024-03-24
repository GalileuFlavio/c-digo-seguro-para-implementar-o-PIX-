# c-digo-seguro-para-implementar-o-PIX-
Demonstra como gerar um QR Code PIX usando a biblioteca qrcode e como validar uma transação PIX recebida:

const qr = require('qrcode');

// Dados da transação PIX
const chavePix = 'chave@exemplo.com';
const valor = 100.00;
const descricao = 'Pagamento do Produto X';

// Montar payload da transação PIX
const payload = {
    pixKey: chavePix,
    amount: valor,
    txId: Math.floor(Math.random() * 1000000), // ID da transação gerado aleatoriamente
    currency: 'BRL',
    description: descricao
};

// Gerar o QR Code PIX
qr.toDataURL(JSON.stringify(payload), (err, url) => {
    if (err) throw err;
    console.log(url);
});
