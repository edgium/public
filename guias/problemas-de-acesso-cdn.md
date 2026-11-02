# Problemas de acesso a um site na CDN: o que coletar e enviar

Este guia mostra quais informações reunir quando um site que passa pela CDN da Edgium fica lento, com erro ou inacessível. Com esses dados em mãos, a análise e a solução ficam mais rápidas.

Se o problema aconteceu com um cliente ou usuário seu, peça a ele os dados abaixo.

---

## 1. Dados de quem está com o problema

Assim conseguimos ver se o problema é de uma região ou de uma rede específica.

- **Provedor de internet:** o nome da operadora usada no momento do problema.
- **Endereço IP:** acesse [meuip.com.br](https://meuip.com.br) e informe o endereço exibido na página.

---

## 2. Diagnóstico de rede

Estes testes mostram o caminho entre quem acessa e a CDN, e onde pode haver falha ou demora. Basta usar uma das opções.

### Traceroute

Mostra cada ponto de passagem até o site.

- **Windows:** abra o Prompt de Comando e execute:

  ```bash
  tracert www.exemplo.com.br
  ```

- **macOS ou Linux:** abra o Terminal e execute:

  ```bash
  traceroute www.exemplo.com.br
  ```

Troque `www.exemplo.com.br` pelo endereço com problema, copie o resultado e envie.

### WinMTR

Para um diagnóstico mais detalhado no Windows, use o [WinMTR](https://sourceforge.net/projects/winmtr/), ferramenta gratuita que combina traceroute e ping.

1. Baixe e abra o WinMTR.
2. Informe o endereço do site com problema e inicie o teste.
3. Deixe rodar por alguns minutos, enquanto o problema está acontecendo.
4. Copie ou salve o resultado e envie.

---

## 3. Detalhes do problema

- **Endereço exato:** a URL completa onde o problema ocorre, por exemplo `https://www.exemplo.com.br/pedidos`.
- **Prints da tela:** capturas do erro no navegador, mostrando o endereço e a mensagem ou o código de erro.
- **Quando aconteceu:** data e horário aproximados, e se ainda está acontecendo.

---

## 4. Cabeçalhos HTTP (opcional)

Estes dados ajudam a identificar como a CDN tratou aquele acesso.

1. No navegador, abra a página com problema.
2. Pressione `F12` para abrir as Ferramentas do Desenvolvedor.
3. Vá para a aba **Rede** (ou **Network**).
4. Recarregue a página e clique na primeira linha, que corresponde ao endereço acessado.
5. Em **Cabeçalhos de resposta**, copie os valores de:
   - `edgium-x-cache`
   - `edgium-x-vision`

Exemplo do formato:

```
edgium-x-cache: HIT
edgium-x-vision: 000000.00000000000000000000000000000000.https.xxx.00000000-0000-0000-0000-000000000000
```

---

## 5. Para onde enviar

Envie tudo para **suporte@edgium.net**. No nosso sistema de chamados, você acompanha o atendimento do início ao fim.

Modelo para copiar:

```
Endereço com problema:
Data e horário:
Provedor de internet:
Endereço IP:
Resultado do traceroute ou WinMTR:
edgium-x-cache (opcional):
edgium-x-vision (opcional):
Prints: em anexo
```

**Dica:** antes de enviar, confira o [Analytics do painel](../painel/2026-11/README.md#3-analytics). A área **Saúde da origem** e o guia de erros muitas vezes já mostram se o problema está no servidor do site ou na rede.
