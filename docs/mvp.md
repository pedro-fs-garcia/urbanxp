# **Roteiro do MVP – UrbanXP**

### **Objetivo do MVP**

Validar se usuários querem **descobrir rolês e eventos locais com recomendações personalizadas**, incluindo a experiência coletiva com amigos, e medir engajamento inicial.

---

## **1️⃣ Funcionalidades Essenciais do MVP**

Foco apenas no que vai gerar **aprendizado real sobre o interesse do usuário**:

1. **Input de intenção**

   * Usuário digita ou grava áudio: “Quero sair sexta à noite com jantar + música ao vivo”.
   * Pode usar filtros simples (tipo de experiência, preço, localização).
   * **Por que:** Testa se o público entende e quer usar o app.

2. **Sugestões de rolê (roteiro básico)**

   * Mostrar 3–5 lugares/eventos próximos, com:

     * Nome do lugar/evento
     * Endereço
     * Preço médio ou ticket
     * Link externo para reservas/ingresso
   * **Por que:** Testa se usuários confiam na recomendação.

3. **Multiusuário simplificado**

   * Usuário pode convidar 1–3 amigos via link ou código.
   * Amigos podem dar 👍 ou 👎 nas sugestões.
   * **Por que:** Valida a experiência social.

4. **Eventos locais**

   * Listar 1–2 eventos da cidade (integrar Sympla/Eventbrite ou manual para começar).
   * **Por que:** Testa interesse em combinar restaurantes + eventos.

5. **Reserva simples**

   * Apenas redirecionamento para site do parceiro (sem integração de pagamento ainda).
   * **Por que:** Testa intenção de compra sem complexidade técnica.

---

## **2️⃣ Tecnologias sugeridas para MVP**

Foco em **rápido, barato e fácil de aprender**:

* **Frontend:** React Native (Android + iOS com um código só).
* **Backend:** Node.js + Express ou Firebase (mais rápido e sem servidor).
* **Banco de dados:** Firebase Firestore ou PostgreSQL simples.
* **Integrações externas:**

  * Google Maps API (endereços, distâncias)
  * Sympla/Eventbrite (eventos)
  * OpenTable/TheFork ou links diretos de restaurantes
* **Prototipação rápida:** Figma para criar telas antes de codificar.

---

## **3️⃣ Testes e Validação**

* **Usuários-alvo:** amigos, colegas e pequenos grupos locais (10–30 pessoas).
* **Objetivo da validação:** medir se usam o app, se compartilham com amigos e se seguem as sugestões.
* **Métricas simples:**

  * Quantidade de pedidos de rolê enviados.
  * % de amigos que interagem com o roteiro.
  * Clique nos links de reserva/evento.
  * Feedback qualitativo via formulário rápido.

---

## **4️⃣ Entregáveis do MVP**

* App funcional com telas básicas: input de intenção, sugestões de rolê, votação de amigos.
* Banco de dados com registro de usuários e preferências.
* Dashboard simples para acompanhar métricas de uso.
* Protótipo visual no Figma para iterar o design.

---

## **5️⃣ Estratégia Pós-MVP**

* Coletar feedback e ajustar funcionalidades:

  * Adicionar recomendações de IA mais avançadas.
  * Melhorar multiusuário e reservas integradas.
  * Gamificação (pontos, badges).
* Decidir expansão regional (SP e outras cidades próximas) com base na aceitação inicial.

