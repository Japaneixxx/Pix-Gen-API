# Pix-Gen-API
[![](https://jitpack.io/v/Japaneixxx/Pix-Gen-API.svg)](https://jitpack.io/#Japaneixxx/Pix-Gen-API)


API simples para geração de código "PIX Copia e Cola" (BR Code) de forma dinâmica e funcional.

## 📝 Descrição

Este projeto consiste em uma API desenvolvida em Java que gera uma string de payload para um QR Code PIX. A partir de informações essenciais como chave PIX, valor, nome do recebedor e cidade, a API monta o payload formatado de acordo com as especificações do Banco Central do Brasil (BACEN), pronto para ser utilizado em pagamentos.

O principal objetivo é facilitar a integração de pagamentos PIX em outras aplicações, abstraindo a complexidade da geração do BR Code.

## 🚀 Como Usar

Para gerar um código "PIX Copia e Cola", basta utilizar a função `generatePayload`. Ela é o coração desta API e responsável por montar a string final.

### Função Principal

```java
generatePayload(String pixKey, BigDecimal amount, String merchantName, String merchantCity, String txid)
```

### Parâmetros

| Parâmetro      | Tipo         | Descrição                                                                                               | Obrigatório |
|----------------|--------------|---------------------------------------------------------------------------------------------------------|-------------|
| `pixKey`       | `String`     | A chave PIX do recebedor (CPF, CNPJ, E-mail, Telefone ou Chave Aleatória).                                  | Sim         |
| `amount`       | `BigDecimal` | O valor da transação.                                                                                   | Sim         |
| `merchantName` | `String`     | O nome do titular da chave PIX que receberá o pagamento.                                                  | Sim         |
| `merchantCity` | `String`     | A cidade do titular da conta.                                                                           | Sim         |
| `txid`         | `String`     | Um identificador único para a transação. Se não for necessário, pode ser passado como `***`. | Sim         |

### ☕ Exemplo de Código em Java

Abaixo está um exemplo prático de como chamar a função para gerar o seu payload.

```java
import java.math.BigDecimal;

public class ExemploPix {

    public static void main(String[] args) {
        // Dados da transação
        String chavePix = "seu-email@exemplo.com";
        BigDecimal valor = new BigDecimal("150.75");
        String nomeRecebedor = "Nome Completo do Recebedor";
        String cidadeRecebedor = "SAO PAULO";
        String idTransacao = "TX12345ABC"; // ou "***" para um ID não único

        // Supondo que a função 'generatePayload' esteja em uma classe chamada 'PixGenerator'
        // PixGenerator pixGenerator = new PixGenerator();
        // String pixCopiaECola = pixGenerator.generatePayload(chavePix, valor, nomeRecebedor, cidadeRecebedor, idTransacao);

        // Imprimindo o resultado
        // System.out.println("Seu PIX Copia e Cola é:");
        // System.out.println(pixCopiaECola);
    }

    // Você precisará incluir a sua função 'generatePayload' aqui ou em uma classe separada.
    public String generatePayload(String pixKey, BigDecimal amount, String merchantName, String merchantCity, String txid) {
        // A lógica da sua função para gerar o payload do PIX viria aqui.
        // ...
        return "payload_gerado_aqui";
    }
}
```

## 🤝 Contribuição

Contribuições são sempre bem-vindas\! Se você tiver alguma ideia para melhorar este projeto, sinta-se à vontade para criar um *fork* do repositório e abrir um *pull request*.

1.  Faça um *fork* do projeto.
2.  Crie uma nova *branch* (`git checkout -b feature/sua-feature`).
3.  Faça o *commit* de suas alterações (`git commit -m 'Adiciona nova feature'`).
4.  Faça o *push* para a *branch* (`git push origin feature/sua-feature`).
5.  Abra um *Pull Request*.

## 📄 Licença

Este projeto pode ser distribuído sob a licença [MIT](https://choosealicense.com/licenses/mit/). Você pode adicionar um arquivo `LICENSE` ao seu projeto com o conteúdo da licença.

-----

### Sugestões Adicionais:

  * **Instalação:** Se o seu projeto usa alguma ferramenta de gerenciamento de dependências como Maven ou Gradle, seria ótimo adicionar uma seção "Instalação" explicando como um usuário pode baixar e configurar o projeto (ex: `mvn install`).
  * **Endpoints da API:** Se você expôs essa função como um endpoint de API (ex: `POST /api/pix`), é muito importante documentar isso com o método HTTP, a URL, o corpo da requisição (`body`) esperado e um exemplo de resposta (`response`).
