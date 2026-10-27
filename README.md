# Operação Contratação Língua Viva

Jogo de apoio à dinâmica do Grupo 6 (Gestão de Pessoas II). Cada jogador envia as notas do próprio celular, o mestre registra a decisão da mesa e o placar atualiza ao vivo.

## 1. Criar o banco gratuito (Firebase, 5 minutos)

1. Acesse console.firebase.google.com e crie um projeto (pode desativar o Analytics).
2. Menu **Build > Realtime Database > Create Database**. Escolha qualquer região e o modo **teste**.
3. Na aba **Rules**, cole e publique:
   ```json
   { "rules": { "salas": { ".read": true, ".write": true } } }
   ```
4. Copie o endereço que aparece no topo da aba **Data**, no formato `https://SEU-PROJETO-default-rtdb.firebaseio.com`.
5. Abra o `index.html`, localize `const DB_URL=""` e cole o endereço entre as aspas.

## 2. Publicar no GitHub Pages

1. Crie um repositório e envie o `index.html`.
2. Em **Settings > Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. O link será `https://SEU-USUARIO.github.io/NOME-DO-REPO/`. Gere um QR code dele para os slides.
4. Para separar o ensaio do dia da apresentação, use salas diferentes: `...?sala=ensaio` e `...?sala=10nov`.

## 3. Como usar na dinâmica

- **Jogadores (34 celulares):** abrem o link, aba **Jogador**, escolhem a mesa, dão as notas 1 a 5 para A e B nas 3 competências e tocam em **Enviar**. Podem reenviar para corrigir.
- **Mestre de cada mesa:** aba **Mestre**. Vê os jogadores da mesa chegando ao vivo, marca as competências e o STAR, escolhe A ou B e registra a decisão.
- **Mestre de fechamento:** aba **Placar** (atualiza a cada 3 segundos, pode projetar). Mostra ranking, contagem de A e B e a mensagem do efeito halo. **Baixar CSV** guarda o resultado.

## Pontuação (máximo 8 por mesa)

- 1 ponto por competência comportamental bem escolhida (até 3).
- 2 pontos se as perguntas seguiram situação, ação e resultado.
- 3 pontos se a decisão foi a do candidato com a maior soma de notas dos jogadores (soma empatada não pontua).

Desempate: decisão alinhada, depois STAR, depois número da mesa.

## Observações

- Sem a configuração do Firebase o jogo roda em modo local (um aparelho só), útil para testar.
- As regras acima deixam qualquer pessoa com o link ler e escrever. Para uma aula é suficiente. Depois do evento, apague o banco ou troque as regras para `false`.
- Use **Zerar jogo** no Placar entre o ensaio e a apresentação, ou simplesmente troque a sala.
