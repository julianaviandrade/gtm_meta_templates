# Templates de Código JavaScript para Meta Ads (Facebook Pixel) no Google Tag Manager

---

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

---

## Eventos Personalizados

Para rastrear ações específicas que não fazem parte dos eventos padrão, use eventos personalizados.

```javascript
fbq('trackCustom', 'NomeDoEvento', {param1: 'valor1', param2: 123});

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
