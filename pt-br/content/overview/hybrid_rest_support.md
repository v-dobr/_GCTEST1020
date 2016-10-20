# <a name="use-rest-apis-to-access-mailboxes-in-exchange-hybrid-deployments-(preview)"></a>Usar APIs REST para acessar caixas de correio em implantações híbridas do Exchange (visualização)

O Microsoft Graph sempre forneceu acesso a caixas de correio do cliente na nuvem no Exchange Online como parte do Office 365. A CU3 (atualização cumulativa 3) do Exchange 2016, lançada em setembro de 2016 para os servidores do Exchange no local, adiciona suporte à integração da API REST com o Office 365. Se o seu aplicativo usa a versão 1.0 da API de [Email](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/message), [Calendário](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/calendar) ou [Contatos](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/contact), agora você também encontrará uma experiência integrada de aplicativo e autenticação em implantações _híbridas_, independentemente de a caixa de correio estar no local ou na nuvem, desde que a implantação atenda a [requisitos](#requirements-for-rest-api-to-work-in-hybrid-deployments) específicos. 


Nos bastidores, quando o Microsoft Graph identifica que uma chamada à API REST está tentando acessar uma caixa de correio no local em uma implantação híbrida, ele cria um proxy da solicitação REST para um ponto de extremidade REST local, que processa a solicitação. Essa descoberta possibilita o acesso à API REST.

>**Observação:** A capacidade de usar essas APIs REST em implantações híbridas está, atualmente, no modo de visualização.

>Somente a versão 1.0 da API de Email, Calendário e Contatos está disponível para caixas de correio em implantações híbridas. Outros conjuntos de API da versão 1.0, como a API de [Grupos](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/group) ou APIs em outras versões, não estão disponíveis. Se tentar usar uma API que não faça parte do conjunto compatível em uma implantação híbrida, você receberá a seguinte mensagem de erro:

>"As APIs REST para essa caixa de correio estão em modo de visualização no momento. Você pode encontrar mais informações sobre as APIs REST de modo de visualização em https://dev.outlook.com."

## <a name="requirements-for-the-rest-api-to-work-in-hybrid-deployments"></a>Requisitos para a API REST funcionar em implantações híbridas

O Microsoft Graph fornece abertura (suporte a padrões abertos como JSON, OAUTH e ODATA, conectando-se à maioria das plataformas conhecidas) e flexibilidade (permissões granulares e rigidamente supervisionadas para acessar dados do usuário). Se sua organização estiver interessada em habilitar o desenvolvimento de aplicativos do Microsoft Graph e atualmente estiver em uma implantação híbrida ou considerando essa opção, esteja ciente dos requisitos de implantação a seguir:

- Requisitos de caixa de correio

  - Todas as caixas de correio locais que usarão as APIs REST devem estar localizadas em bancos de dados localizados em servidores Exchange 2016 CU3. 

- Requisitos de infraestrutura

  - Todos os servidores do Exchange 2016 devem ser atualizados para o CU3 ou posterior.  
  - O Microsoft Active Directory local deve ser sincronizado com o Azure Active Directory.
  - Todos os servidores do Exchange 2013 que coexistem na mesma matriz com carga balanceada com servidores do Exchange 2016 devem ser removidos da matriz.

- Requisitos de rede

  - De uma perspectiva de DNS, o namespace de descoberta automática e o namespace do cliente local devem ter os registros de DNS da Internet. 
  - Se você tiver um firewall ou gateway de aplicativo que inspeciona e restringe o acesso, atualize as configurações apropriadas para permitir o acesso e a descoberta.


Os administradores de TI podem encontrar mais informações nos seguintes recursos:

- 
  [Implantações Híbridas do Exchange Server](https://technet.microsoft.com/en-us/library/jj200581(v=exchg.150).aspx)
- [Lançamento de atualização cumulativa de setembro de 2016](https://blogs.technet.microsoft.com/exchange/2016/09/20/released-september-2016-quarterly-exchange-updates/) 
- [Requisitos de arquitetura local para a API REST](https://blogs.technet.microsoft.com/exchange/2016/09/26/on-premises-architectural-requirements-for-the-rest-api/)
