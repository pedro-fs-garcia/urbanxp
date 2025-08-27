## 7. **Tecnologia**

### 1. **Stack inicial**

* **Frontend mobile:** React Native (cross-platform para iOS e Android, permite desenvolvimento rápido e manutenção simplificada).
* **Backend:** Node.js com NestJS (robusto, modular e escalável, fácil integração com APIs externas).
* **Banco de dados:** PostgreSQL para dados relacionais (usuários, reservas, eventos) + Redis para cache e performance em consultas frequentes.
* **APIs externas:** Integração com Google Maps (geolocalização, distâncias, mapas), Sympla/Eventbrite (eventos e ingressos), OpenTable/TheFork (reservas de restaurantes).
* **IA:** Modelo de recomendação e chat/áudio via API (ex: OpenAI GPT ou outro modelo customizado) para interpretação de linguagem natural e roteiros inteligentes.

**Justificativa:**
Essa stack permite **rápida prototipação**, manutenção simples e escalabilidade conforme usuários e volume de dados crescem.

---

### 2. **Integrações**

* **Google Maps:** localização, cálculo de rotas, distância e geolocalização de eventos e restaurantes.
* **Sympla/Eventbrite:** listagem de eventos, venda de ingressos e redirecionamento ou integração direta.
* **OpenTable/TheFork:** reservas de restaurantes e mesas, informações sobre disponibilidade e horários.
* **Pagamentos:** Stripe, PayPal, Pagar.me ou Mercado Pago para processar reservas e ingressos diretamente no app.
* **APIs de clima/tempo:** para ajustar recomendações de acordo com condições meteorológicas.

**Justificativa:**
Integrações permitem oferecer **experiência completa sem precisar reconstruir toda a infraestrutura de eventos e reservas**, agilizando o MVP e aumentando confiabilidade.

---

### 3. **Infraestrutura**

* **Cloud:** AWS ou GCP (escala de forma elástica, alta disponibilidade e redundância).
* **Serviços principais:**

  * EC2/Compute Engine para backend.
  * S3/Cloud Storage para armazenamento de mídia (imagens, banners, avatars).
  * RDS/Cloud SQL para banco de dados relacional.
  * ElastiCache/Redis para cache de dados de alta frequência.
  * Lambda/Cloud Functions para jobs agendados (ex: notificações de eventos próximos).
* **Escalabilidade futura:**

  * Microserviços para IA, roteiros, reservas e notificações.
  * Kubernetes para orquestração e balanceamento de carga.

**Justificativa:**
Garante que o app possa crescer rapidamente sem reescrever arquitetura, suportando grandes volumes de usuários e parceiros.

---