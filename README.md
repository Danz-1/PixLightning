# PIXLightning ⚡

> Uma maquininha web para receber pagamentos Bitcoin pela Lightning Network — simples, bonita e open source!

![Tela do PIXLightning](./frontend/screenshot.png)

## ✨ Sobre

PIXLightning é um webapp open source que transforma seu computador em uma maquininha de pagamentos Lightning.  
Com ele, qualquer pessoa pode gerar cobranças instantâneas em Bitcoin (LN), sem precisar instalar nada ou pagar taxas absurdas.

### 🎯 Características

- Código **simples** e 100% open source
- Visual de "POS" moderno e fácil de usar
- Integração direta com **LNBits** (FakeWallet para testes, ou node real para produção)
- Perfeito para usar em eventos, feiras, hackathons, ou só para aprender LN!

## 🚀 Como rodar

### **Pré-requisitos**

- Python 3.8+
- Docker (para rodar o LNBits)
- Uma carteira LNBits configurada (pode usar o modo FakeWallet para testar!)

### **Passo 1 — Suba o LNBits**

Clone o repositório do [LNBits](https://github.com/lnbits/lnbits-legend):

```bash
git clone https://github.com/lnbits/lnbits-legend
cd lnbits-legend
docker build -t lnbits .
docker run -d -p 5000:5000 --name lnbits lnbits
```

Acesse http://localhost:5000, crie sua carteira e copie a Invoice Key.

**Dica:** Para testes, ative o FakeWallet nas extensões do LNBits.

### **Passo 2 — Configure e rode o backend**

No diretório `backend/`, instale as dependências:

```bash
pip install -r requirements.txt
```

Abra o arquivo `main.py` e ajuste as variáveis:

```python
LN_BITS_API = "http://localhost:5000"
INVOICE_KEY = "SUA_INVOICE_KEY_AQUI"
```

Rode o backend:

```bash
uvicorn main:app --reload
```

### **Passo 3 — Rode o frontend**

No diretório `frontend/`, inicie um servidor local (exemplo usando Python):

```bash
python -m http.server 8080
```

Acesse http://localhost:8080 e pronto!

## 🖥️ Como usar

1. Digite o valor (em reais) e a descrição da venda
2. Clique em **Gerar cobrança**
3. Mostre o QR code para seu cliente
4. O status muda para "Pagamento recebido!" automaticamente quando o pagamento é detectado

## 🛠️ Customização

- **Conexão com node real:** Basta trocar o FakeWallet pelo seu node Lightning no LNBits
- **Valores mínimos:** Editáveis direto no `index.html` ou backend
- **Layout:** Edite o CSS para adaptar à sua marca ou necessidades

## 📁 Estrutura do Projeto

```
PIXLightning/
├── backend/
│   ├── main.py
│   └── requirements.txt
├── frontend/
│   ├── index.html
│   └── screenshot.png
├── README.md
└── LICENSE
```

## 📷 Screenshot

 `frontend/screenshot.png`

## 📝 Licença

MIT — Sinta-se livre para usar, remixar, contribuir e compartilhar!
