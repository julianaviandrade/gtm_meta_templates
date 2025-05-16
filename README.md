# Templates de Código JavaScript para Meta Ads (Facebook Pixel) no Google Tag Manager

### Do que se trata este projeto?
Este projeto oferece templates em JavaScript para ajudar na implementação e cadastro dos eventos do Meta Pixel utilizando o Google Tag Manager (GTM). Com esse projeto, será possível configurar esses eventos dentro do GTM, sem necessidade de mexer diretamente no código do seu site, tornando a gestão das tags mais simples, organizada e flexível.

### Qual tecnologia é usada neste projeto?
O Google Tag Manager é uma ferramenta que facilita a inserção e gerenciamento de scripts (tags) no seu site. Os templates são códigos JavaScript que você pode utilizar dentro das Tags personalizadas do GTM para enviar os eventos corretamente ao Meta Ads.

### Como funciona os templates no Google Tag Manager?
1) Instalação do Meta Pixel via GTM:
- Você cria uma Tag personalizada no GTM, onde cola o código base do Meta Pixel, que inclui a função >fbq<.
- Essa tag é configurada para ser disparada em todas as páginas, garantindo que o Pixel esteja ativo e pronto para enviar informações.

2) Cadastro de eventos (padrão ou personalizados):
- Para cada evento que deseja rastrear, você cria uma nova Tag do tipo HTML personalizado dentro do GTM contendo o código JavaScript que chama a função fbq('track', ...) para eventos padrão, ou fbq('trackCustom', ...) para eventos personalizados.
- Você configura os gatilhos no GTM que determinam quando esta tag será disparada — por exemplo, em condições específicas como clique em botão, visualização de página específica ou submissão de formulário.

3) Execução e envio dos eventos:
- Quando o gatilho associado à tag é acionado, o GTM executa o código JavaScript da tag, chamando a função fbq correspondente.
- A função fbq envia os dados do evento para o Meta Ads em segundo plano, permitindo que você meça e analise essas ações dentro da plataforma do Meta.

## Eventos Padrão

Os eventos padrão são categorias já reconhecidas pelo Meta para facilitar o rastreamento e otimização. E possuem essa configuração:

| Evento               | Descrição                                   | Exemplo de uso                                      |
|----------------------|---------------------------------------------|----------------------------------------------------|
| **PageView**         | Página visualizada                           | `fbq('track', 'PageView');`                         |
| **ViewContent**      | Visualização de conteúdo específico          | `fbq('track', 'ViewContent', {content_name: 'Produto A'});` |
| **Search**           | Busca realizada                              | `fbq('track', 'Search', {search_string: 'Tênis'});`|
| **AddToCart**        | Item adicionado ao carrinho                  | `fbq('track', 'AddToCart', {content_ids: ['123'], content_type: 'product'});` |
| **AddToWishlist**    | Item adicionado à lista de desejos           | `fbq('track', 'AddToWishlist', {content_ids: ['123']});`|
| **InitiateCheckout** | Início do checkout                           | `fbq('track', 'InitiateCheckout');`                 |
| **AddPaymentInfo**   | Dados de pagamento adicionados                | `fbq('track', 'AddPaymentInfo');`                   |
| **Purchase**         | Compra finalizada                            | `fbq('track', 'Purchase', {value: 30.00, currency: 'BRL'});` |
| **Lead**             | Conquista de lead                            | `fbq('track', 'Lead');`                              |
| **CompleteRegistration**| Cadastro concluído                       | `fbq('track', 'CompleteRegistration');`             |

### Exemplo para Evento Purchase

```javascript
fbq('track', 'Purchase', {
  value: 150.00,
  currency: 'BRL',
  content_ids: ['produto_123'],
  content_type: 'product'
});
````

---


## Eventos Personalizados

Para rastrear ações específicas que não fazem parte dos eventos padrão, use eventos personalizados.

```javascript
fbq('trackCustom', 'NomeDoEvento', {param1: 'valor1', param2: 123});
```
---

## Boas Práticas
- Utilize nomes claros e sem espaços para eventos personalizados (camelCase ou PascalCase).
- Informe parâmetros relevantes para enriquecer seus dados.
- Teste a implementação com o Facebook Pixel Helper .
- Mantenha seu pixel atualizado conforme alterações da plataforma Meta.

---

## Recursos Úteis
- Documentação Meta Pixel
- Lista de Eventos Padrão (Meta)
- Facebook Pixel Helper (Extensão Chrome)
