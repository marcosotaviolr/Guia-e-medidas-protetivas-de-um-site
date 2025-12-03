Este trabalho teve como objetivo analisar o site testphp.vulnweb.com, que é um ambiente criado para estudos de segurança, e identificar vulnerabilidades reais que comprometeriam um sistema em produção. Durante a análise, observamos problemas ligados à falta de criptografia, configurações inadequadas, exposição de informações internas e ausência de práticas essenciais de proteção.

1- A primeira vulnerabilidade percebida foi a ausência de HTTPS. Sem uma conexão segura, qualquer dado enviado pelo usuário inclusive senhas ou informações pessoais  pode ser interceptado com facilidade. A solução para isso é simples e fundamental: instalar um certificado SSL e configurar o servidor para aceitar apenas conexões criptografadas.

2- Outro ponto identificado foi a exposição das versões do servidor e do PHP. Quando um site revela publicamente qual tecnologia e qual versão está utilizando, ele facilita muito o trabalho de um atacante, que pode procurar falhas conhecidas especificamente para aquela versão. No caso analisado, além de a versão estar visível, ela também estava desatualizada. A medida correta é manter tudo atualizado e ocultar esses detalhes internos.

3- A análise também mostrou que os cookies do site não estavam configurados de maneira segura. Cookies são essenciais para manter a sessão do usuário, mas quando não possuem proteções como Secure, HttpOnly e SameSite, podem ser roubados ou utilizados de forma indevida. Configurar esses parâmetros reduz drasticamente o risco de sequestro de sessão.

4- Outro problema é que o site não utiliza cabeçalhos de segurança importantes fornecidos pelos navegadores. Sem esses cabeçalhos, o sistema fica vulnerável a ataques como scripts maliciosos (XSS), páginas falsas dentro da própria página (clickjacking) e interpretações incorretas de arquivos. Implementar esses cabeçalhos no servidor é uma forma prática e eficiente de elevar a segurança.

5- A atualização do sistema como um todo também se mostrou um ponto crítico. Muitos ataques acontecem justamente em sistemas desatualizados, já que as falhas são documentadas e exploradas rapidamente. Manter o servidor, plugins e ferramentas atualizadas é indispensável para evitar problemas conhecidos e para garantir estabilidade.

6- Além disso, reforçamos a importância dos backups. Eles servem como uma garantia caso ocorra qualquer ataque, erro humano ou falha no servidor. O ideal é ter cópias armazenadas em locais diferentes e com versões recentes para permitir a recuperação do sistema sem perdas significativas.

7- Outro tema mencionado foi a hospedagem segura. Uma infraestrutura de hospedagem profissional oferece diversas camadas de proteção, como monitoramento de invasões, backups automáticos, atualizações de segurança e certificado SSL. Isso reduz significativamente os riscos, mesmo para sites pequenos.

8- Por fim, discutimos a diferença entre firewall e antivírus. Embora ambos sejam ferramentas de segurança, eles atuam em camadas diferentes. O antivírus trabalha dentro da máquina, analisando arquivos e removendo ameaças. Já o firewall funciona como uma barreira na porta de entrada da rede, filtrando acessos e bloqueando comportamentos suspeitos antes mesmo de chegarem ao sistema. Juntos, eles aumentam bastante a proteção.

Em geral, a análise mostrou que a segurança de um site não depende de apenas um recurso isolado, mas de um conjunto de práticas contínuas: manter o sistema atualizado, proteger dados com HTTPS, configurar cookies corretamente, aplicar cabeçalhos de segurança, realizar backups regulares e utilizar uma hospedagem confiável. Seguir essas medidas torna qualquer site mais seguro, mais estável e menos vulnerável a ataques.
