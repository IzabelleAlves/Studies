# Diferença entre Cookie e Cache:

- O cookie envia informações para o servidor, enquanto o cache não.

- Cookies armazenam alguns dados do usuário — como login, preferências ou sessão — para que, ao acessar a mesma página novamente, esses dados já estejam “lembrados” e enviados automaticamente pro servidor. É por isso que, depois que a gente faz login e marca a opção "mantenha-me conectado", da próxima vez entramos direto na conta. Isso acontece porque, por trás dos panos, o navegador envia o cookie com nossos dados junto à requisição e o servidor reconhece.

- Já o cache está mais voltado pra performance. Ele salva localmente arquivos estáticos, como HTML, CSS, JS, imagens... e não os dados do usuário em si. O que acontece é que, ao acessar um site, o navegador guarda os conteúdos que o servidor enviou — como banners, estilos e scripts. Assim, quando atualizamos a página, tudo carrega bem mais rápido porque esses arquivos já estão salvos localmente e não precisam ser baixados de novo.
  Mas... se algum banner ou uma imagem for alterado no servidor, ele só vai aparecer atualizado se o navegador entender que precisa puxar de novo — o que pode acontecer com um refresh ou após a expiração do cache. O cache não envia nada ao servidor, ele só recebe os arquivos e guarda localmente pra agilizar o carregamento.

> existem formas de atualizar o cache sem que atualize a página inteira. Usando o cache tags do nextJs
