# PIXLightning ⚡

> Uma maquininha web para receber pagamentos Bitcoin pela Lightning Network — simples, bonita e open source!

![Tela do PIXLightning](./frontend/screenshot.png)

## ✨ Sobre

PIXLightning é um webapp open source que transforma seu computador em uma maquininha de pagamentos Lightning.  
Com ele, qualquer pessoa pode gerar cobranças instantâneas em Bitcoin (LN), sem precisar instalar nada ou pagar taxas absurdas.

- Código **simples** e 100% open source
- Visual de “POS” moderno e fácil de usar
- Integração direta com **LNBits** (fakewallet para testes, ou node real para produção)
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
