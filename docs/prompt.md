# Prompt para Geração de Frontend React Native (Expo + TypeScript) – UrbanXP

Você é um(a) engenheiro(a) sênior de React Native. Crie o app **UrbanXP** (MVP) usando **Expo + React Native + TypeScript**, com código limpo, modular, testável e acessível.

**UrbanXP** – Concierge inteligente de experiências e roteiros.

**Propósito central:**
O UrbanXP tem como objetivo transformar a forma como pessoas descobrem e planejam experiências de lazer em suas cidades. Ele combina recomendações personalizadas de restaurantes, bares, eventos culturais e esportivos, criando roteiros completos que consideram preferências individuais e de grupos. O app visa economizar tempo, reduzir a indecisão e tornar a saída social mais prazerosa, ao mesmo tempo em que integra reservas e ingressos dentro da plataforma, monetizando comissões e parcerias.

**Público-alvo:**

* Jovens e adultos de 18 a 40 anos em grandes centros urbanos (SP, RJ, BH, Porto Alegre, etc.).
* Grupos de amigos que buscam experiências compartilhadas.
* Casais ou pessoas que procuram experiências personalizadas (jantar romântico, música ao vivo, feiras).
* Turistas que querem descobrir opções de lazer confiáveis e adaptadas aos seus gostos.
* Pequenos eventos e estabelecimentos que desejam divulgar suas experiências para públicos segmentados.

## Objetivo do App
UrbanXP ajuda pessoas a encontrarem rolês e eventos próximos, com recomendações inteligentes baseadas nas preferências de uma pessoa ou de um grupo de amigos. O MVP deve cobrir: filtragem para geração das sugestões, sugestões, votação em grupo, roteiro final e redirecionamento para reserva/ingresso.


**Dor do usuário:**

* Dificuldade em decidir para onde sair ou qual experiência escolher, especialmente em grupos.
* Falta de integração entre informações de restaurantes, bares e eventos culturais.
* Tempo gasto pesquisando e comparando opções em múltiplos sites/aplicativos.
* Incerteza sobre se a escolha vai agradar todos do grupo.
* Pouca personalização em recomendações de lazer, resultando em escolhas repetitivas ou insatisfatórias.


## **Proposta de Valor**

**O que o app entrega de único:**

* Experiências de lazer totalmente personalizadas, considerando preferências individuais e coletivas.
* Combina recomendações de restaurantes, bares e eventos locais em **roteiros completos e contextuais**.
* Permite reservar mesas e ingressos diretamente no app, com integração a parceiros.
* Possibilita votação e ajustes em grupo, garantindo que o roteiro agrade a todos.
* Oferece feedback contínuo para melhorar futuras recomendações.

**Benefícios principais:**

* Redução do tempo gasto decidindo onde ir e o que fazer.
* Experiências mais satisfatórias e memoráveis para indivíduos e grupos.
* Descoberta de novos lugares e eventos na cidade, ampliando o repertório de lazer.
* Facilidade de uso com interface intuitiva e integração com serviços de reserva e pagamento.
* Engajamento social e compartilhamento entre amigos, estimulando crescimento orgânico do app.


## Requisitos Técnicos
- **Expo** (SDK mais recente) + **TypeScript** estrito.
- **React Navigation v6** (Stack + Bottom Tabs).
- **NativeWind** (Tailwind para RN) para estilos.
- **Zustand** para gerenciamento de estado.
- **TanStack Query (react-query)** para fetch/cache, mesmo com mocks.
- **AsyncStorage** para persistência local (histórico, preferências).
- **react-native-maps** para mapas + integração com “abrir no Maps”.
- **axios** para requisições HTTP (inclusive mocks).
- **expo-constants** para env/config (criar `env.example.ts`).
- **Jest + @testing-library/react-native** para testes (mínimo 5).
- **ESLint + Prettier** para qualidade de código.
- **Acessibilidade**: use `accessibilityLabel`, `accessible`, `testID` em elementos interativos.
- **Tailwind config centralizada** para tokens de cor, tipografia e espaçamento.
- **Temas claro/escuro** via Context + NativeWind, com alternância dinâmica.
- **Estrutura pronta para internacionalização** (pt-BR padrão, en-US preparado).
- **Componentização**: crie componentes base reutilizáveis (Button, Input, Card, etc).
- **Design jovem, urbano e vibrante**, com animações suaves e ícones minimalistas (ex: lucide-react-native).

## Estrutura de Pastas

```
/src
  /app (rotas do Expo Router OU /navigation – documente a escolha)
  /components
  /screens
  /modules (feature-based: discover, suggestions, friends, itinerary, profile)
  /services (api, mocks)
  /store (zustand)
  /hooks
  /assets (ícones, imagens)
  /theme (tokens tailwind + constantes)
  /utils
  /types
  /i18n (pt-BR, pronto para en-US)
  /tests
```

## Design System (Tokens)
- **Cores**: primary(#5B8DEF), secondary(#0FC2C0), bg(#0B0E14), card(#151A24), text(#EAECEE), muted(#9AA4B2), success(#30D158), warning(#FFC542), danger(#FF5A5F).
- **Espaçamento**: 4,8,12,16,20,24.
- **Tipografia**: título, subtítulo, corpo, caption (usar família padrão do RN).
- **Componentes base**: Button (primário/secundário/destructive/ghost), Input (com ícone), Chip/Tag, Card, RatingStars, PriceBadge, EmptyState, ErrorState, Loader (skeleton/shimmer), MapPreview, VoteBar, SectionHeader.

TELAS PRINCIPAIS (com critérios de aceite)
1) **Onboarding/Login (mock)**
   - Input nome e um botão “Entrar” (mock).
   - Salvar perfil mínimo em AsyncStorage.
   - Botão “Pular” para ir direto ao app.
   - Acessibilidade: labels em todos inputs/botões.

2) **Home/Descobrir**
   - Header: “Para onde vamos hoje?”
   - **Entrada por chat** (textarea + botão enviar) e **botão microfone** (stub de voz que preenche o input com texto simulado).
   - Chips de filtros rápidos: {Jantar, Bar, Música ao vivo, Dançar, Orçamento baixo/$$$ , Distância <2km, Hoje/Este fim-de-semana}.
   - CTA “Gerar sugestões”.
   - Estados: vazio (EmptyState com CTA), carregando (skeleton), erro (retry).
   - Aceite: ao enviar intenção → navega para “Sugestões”.

3) **Sugestões (lista + mapa)**
   - Tab/segmented control: **Lista** | **Mapa**.
   - Cards com: nome, tipo (restaurante/bar/evento), nota (★), faixa de preço (R$-R$$$), distância, horário, tags (veg/ao vivo/pet friendly), botão 👍/👎.
   - BottomSheet de detalhes: fotos (placeholders), descrição, link “Ver no mapa”, “Reservar/Ingressos”.
   - Botão “Convidar amigos” abre fluxo de convite.
   - Aceite: votar muda barra de “match do grupo”; “Ver no mapa” abre MapView com pins.

4) **Amigos/Convites (multiusuário simplificado)**
   - Gerar **código de sessão** (ex: UX1234) e **link mágico** (simulado).
   - Campo para **entrar em sessão** com código.
   - Lista de amigos na sessão com “preferências resumidas” (ex: veg, rock, budget).
   - Aceite: ao amigo entrar, store do grupo atualiza e Sugestões recalculam (mock via função).

5) **Roteiro Final**
   - “Top escolha do grupo” (baseada na soma de votos).
   - Passos do roteiro (ex: Jantar → Show → After).
   - Ações: **Abrir no Maps**, **Reservar/Ingressos** (link externo), **Compartilhar** (Share API).
   - Mostrar tempo/distância entre passos (mock com Haversine relativo).
   - Aceite: compartilhar cria um texto com nome dos locais e links.

6) **Perfil & Histórico**
   - Preferências: orçamento (slider), estilos (checkbox chips), restrições alimentares, horário favorito.
   - Histórico de rolês: cards com data + avaliação rápida (👍/👎).
   - Sair da conta (limpar AsyncStorage).
   - Aceite: ao salvar preferências, recomputar “sugestões” (mock).

7) **Notificações (lista simples)**
   - Sugestões contextuais (mock) “Hoje sem chuva: trilha + bar com música”.
   - Aceite: tocar em notificação → abre detalhes.

FUNCIONALIDADES TRANSVERSAIS
- **Chat de intenção**: parse simples (mock) que transforma texto em objeto de filtros (tipo, orçamento, distância, data).
- **Áudio**: clique preenche o input com um texto simulado (“Quero jantar vegano e música ao vivo”).
- **Combinação de preferências do grupo**: função `mergeGroupPreferences(members)` (média de orçamentos, interseção de estilos, veto a restrições).
- **Votação**: store registra votos por item e membro; calcula “score” e top 1.
- **Gamificação leve**: ao fazer check-in (botão no card de detalhes), somar 10 pontos no perfil (mock).
- **Links externos**: `Linking.openURL()` para reservas/ingressos.

## Tipos (TypeScript)
Defina tipos em `/types`. Exemplo:
```ts
export type ExperienceType = 'restaurant' | 'bar' | 'event';
export interface Place {
  id: string;
  type: ExperienceType;
  name: string;
  description: string;
  address: string;
  lat: number;
  lng: number;
  priceLevel: 1 | 2 | 3; // R$-R$$$
  rating: number; // 0-5
  tags: string[];
  distanceKm?: number;
  photos?: string[];
  externalUrl?: string; // reserva/ingressos
  startTime?: string;   // eventos
}
export interface UserProfile {
  id: string;
  name: string;
  budget: number; // em R$
  styles: string[]; // ['rock','electro','romantic','craft-beer']
  dietary?: string[]; // ['vegetarian','vegan','gluten-free']
  preferredHours?: string[]; // ['evening','night','weekend']
  points?: number;
}
export interface GroupSession {
  code: string;
  ownerId: string;
  memberIds: string[];
  votes: Record<string, 1 | -1 | 0>; // por item (compose chave `itemId:userId`)
  suggestions: Place[];
}
export interface IntentFilters {
  text: string;
  types?: ExperienceType[];
  maxDistanceKm?: number;
  budget?: number;
  date?: string; // ISO
  tags?: string[];
}
```

## Serviços (Mocks)
- `/services/mockData.ts`: 10–15 `Place` variados.
- `/services/api.ts`: funções assíncronas com `setTimeout` (600–1200ms):
  - `fetchSuggestions(filters, group?)`
  - `fetchEvents(city, date?)`
  - `reserve(placeId)`
- `/services/geo.ts`: função para distância (Haversine) e ordenação por proximidade.

## Store (Zustand)
- `/store/app.ts`: currentUser, group, setUser, updatePreferences, createGroup, joinGroup, leaveGroup, setSuggestions, vote, selectTopChoice. Persistência parcial em AsyncStorage.

## Regras de UX/Estados
- Toda tela: loading, success, empty, error.
- Skeletons para loading, EmptyState com CTA, erro com retry.

## Mapa
- Sugestões > Mapa: MapView com pins, BottomSheet ao tocar, botão “Ir” abre Google Maps.

## Internacionalização
- `i18n/pt-BR.ts` com todas as strings.
- `i18n/index.ts` pronto para en-US (usar pt-BR por padrão).

## Analytics (Stubs)
- `analytics.ts` com funções de tracking (console.log).

## Acessibilidade e Testes
- Botões/inputs com `accessibilityLabel` e `testID`.
- Testes para: render Home/intenção, Sugestões, votação, sessão, itinerário.

## Navegação (Sugestão)
- Bottom Tabs: Descobrir, Amigos, Perfil
- Stacks: DiscoverStack, FriendsStack, ProfileStack
- Deep links (stub): `urbanxp://intent`, `urbanxp://group/UX1234`

## Aspectos Visuais e UI
- Visual jovem, urbano, vibrante, claro.
- Cards arredondados, sombras suaves, ícones minimalistas.
- Tipografia legível, títulos em negrito.
- Animações suaves, ripple em botões, carrossel animado.

## Funcionalidades Extras (Placeholder)
- Placeholder para integrações futuras (parceiros, notificações push, login social).

## Expectativa de Código
- Código bem comentado, modular, escalável.
- Componentes reutilizáveis, padrão consistente.
- Tailwind centralizado para tokens.
- Temas claro/escuro expansíveis.
- Pronto para integração futura de backend.

## Comandos
- Gerar projeto Expo + RN TS.
- Instalar dependências mencionadas.
- Adicionar scripts npm: start, test, lint, typecheck.
- Incluir `README.md` com: setup, env, scripts, estrutura, como rodar testes.

## Critérios de Entrega
- Projeto compila e roda no Expo Go.
- Fluxo completo: Login (mock) → Descobrir → Sugestões (lista/mapa + votos) → Convidar amigos (código) → Roteiro final (abrir no Maps/reserva) → Histórico.
- Código tipado, componentes reutilizáveis, store organizada, mocks funcionando, testes passando.
- README com GIFs/descrições (screenshots automáticos não obrigatórios).

## Bônus (Se Couber)
- Tema claro/escuro via Context + NativeWind.
- Persistência de histórico com paginação simples.
- Componente `VoiceButton` isolado.

## Importante
- Não use bibliotecas abandonadas.
- Não bloqueie o fluxo por falta de backend; mocks bem estruturados em `/services`.
- Comente pontos de integração real (Maps, Sympla/Eventbrite, reservas).
- Entregue o projeto completo, incluindo exemplos de mocks, testes e README.

