# 🚀 Automação de Disparo em Massa WhatsApp (n8n + Evolution API)

Este projeto apresenta um workflow para o **n8n** focado no envio seguro e automatizado de mensagens de prospecção via WhatsApp. Utiliza a **Evolution API** para a comunicação e o **Google Sheets** como base de dados e controlo de envio.

## 📋 Funcionalidades

- **Gestão via Google Sheets:** Lê os contactos diretamente da tua folha de cálculo.
- **Controlo de Status:** Verifica se a mensagem já foi enviada para evitar duplicados.
- **Sistema Anti-Ban:** Intervalos de espera (Wait Node) configuráveis entre cada disparo para proteger o teu número.
- **Loop Inteligente:** Processa um contacto de cada vez de forma sequencial.
- **Atualização Automática:** Após o envio, o fluxo volta à folha de cálculo e marca o contacto como "Enviado".

## 🛠️ Requisitos

- [n8n](https://n8n.io/) instalado.
- [Evolution API](https://evolution-api.com/) configurada e ligada a uma instância de WhatsApp.
- Uma folha de cálculo no Google Sheets com as colunas: `NOME`, `TELEFONE` e `STATUS`.

## 🚀 Como Instalar

1. **Importar o JSON:**
   - Descarrega o ficheiro `.json` deste repositório.
   - No teu n8n, cria um novo workflow e seleciona **Import from File**.

2. **Configurar Credenciais:**
   - No nó do **Google Sheets**, liga a tua conta Google.
   - No nó da **Evolution API**, insere a tua URL e a `apikey` da tua instância.

3. **Ajustar Variáveis:**
   - No nó de envio de mensagem, verifica se os campos `{{ $json.NOME }}` e `{{ $json.TELEFONE }}` correspondem aos nomes das colunas na tua folha de cálculo.

## ⚠️ Segurança (Importante)

Para evitar o banimento do seu WhatsApp:
- Recomenda-se configurar o nó de **Espera (Wait)** para um intervalo entre **180 a 300 segundos**.
- Utilize um texto humanizado e evite disparos para listas de contactos que nunca interagiram contigo.

---

### 📄 Licença
Este projeto é para fins educativos. O uso de ferramentas de automação deve respeitar os Termos de Serviço do WhatsApp. O autor não se responsabiliza por eventuais bloqueios de conta.
