# <a name="getting-started-building-microsoft-graph-apps"></a>Начало создания приложений Microsoft Graph

Статьи, перечисленные в этом разделе, содержат подробные указания по созданию приложений для подключения к Microsoft Graph на различных языках и платформах разработки. Каждая статья начинается с простого начального проекта для соответствующей платформы и содержит указания по добавлению функций проверки подлинности пользователя и отправки в службу Microsoft Graph простого запроса на отправку электронного сообщения со своей учетной записи. Готовый проект идентичен [примеру Connect в репозитории Microsoft Graph](https://github.com/microsoftgraph?utf8=%E2%9C%93&query=connect) для соответствующей платформы.

Выберите статью, посвященную выбранным вами поставщику проверки подлинности и платформе разработки, и приступайте к подключению к Microsoft Graph.

Вы можете выполнить действия, указанные в статье, посвященной вашей платформе разработки, либо воспользоваться [кратким руководством](http://dev.office.com/getting-started/office365apis), чтобы быстро подготовить решение к работе.

Готовые примеры Connect вы найдете в [репозитории Microsoft Graph ](https://github.com/microsoftgraph) на сайте GitHub. Ниже представлены примеры для разных поставщиков проверки подлинности и платформ, а также указано, что они используют для подключения к Microsoft Graph: REST или клиентскую библиотеку Microsoft Graph.

<table>
  <tr>
    <th>Платформа</th>
    <th>Конечная точка Azure AD</th> 
    <th>Конечная точка Azure AD версии 2.0</th>
  </tr>
  <tr>
    <td>Android</td>
    <td>Пример с использованием 
        <a href="https://github.com/microsoftgraph/android-java-connect-rest-sample">REST</a> или <a href="https://github.com/microsoftgraph/android-java-connect-sample/tree/last_v1_auth">пакета SDK</a>
    </td> 
    <td>
        <a href="https://github.com/microsoftgraph/android-java-connect-sample">Пример с использованием пакета SDK</a>
    </td> 
  </tr>
  <tr>
    <td>AngularJS</td>
    <td>
        <a href="https://github.com/microsoftgraph/angular-connect-rest-sample/tree/last_v1_auth">Пример с использованием REST</a>
    </td> 
    <td>Пример с использованием 
        <a href="https://github.com/microsoftgraph/angular-connect-rest-sample">REST</a> или <a href="https://github.com/microsoftgraph/angular-connect-sample">пакета SDK</a>
    </td> 
  </tr>
  <tr>
    <td>ASP.NET</td>
    <td>
        <a href="https://github.com/microsoftgraph/aspnet-connect-rest-sample">Пример с использованием REST</a>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/aspnet-connect-sample">Пример с использованием пакета SDK</a>
    </td> 
  </tr>
  <tr>
    <td>iOS (Obj-C)</td>
    <td>
        <a href="https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample">Пример с использованием REST</a>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/ios-objectivec-connect-sample">Пример с использованием пакета SDK</a>
    </td> 
  </tr>
  <tr>
    <td>iOS (Swift)</td>
    <td>
        <a href="https://github.com/microsoftgraph/ios-swift-connect-rest-sample">Пример с использованием REST</a>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/ios-swift-connect-sample">Пример с использованием пакета SDK</a>
    </td> 
  </tr>
  <tr>
    <td>NodeJS</td>
    <td>
        <a href="https://github.com/microsoftgraph/nodejs-connect-rest-sample/tree/last_v1_auth">Пример с использованием REST</a>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/nodejs-connect-rest-sample">Пример с использованием REST</a>
    </td> 
  </tr>
  <tr>
    <td>PHP</td>
    <td>
        <a href="https://github.com/microsoftgraph/php-connect-rest-sample/tree/last_v1_auth">Пример с использованием REST</a>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/php-connect-rest-sample">Пример с использованием REST</a>
    </td> 
  </tr>
  <tr>
    <td>Python</td>
    <td>
        <a href="https://github.com/microsoftgraph/python3-connect-rest-sample">Пример с использованием REST</a>
    </td>     
    <td>
    </td> 
  </tr>
  <tr>
    <td>Ruby</td>
    <td>
        <a href="https://github.com/microsoftgraph/ruby-connect-rest-sample/tree/last_v1_auth">Пример с использованием REST</a>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/ruby-connect-rest-sample">Пример с использованием REST</a>
    </td> 
  </tr>
  <tr>
    <td>UWP</td>
    <td>
        <a href="https://github.com/microsoftgraph/uwp-csharp-connect-rest-sample/tree/last_v1_auth">Пример с использованием REST</a>
    </td>     
    <td>Пример с использованием 
        <a href="https://github.com/microsoftgraph/uwp-csharp-connect-rest-sample">REST</a> или <a href="https://github.com/microsoftgraph/uwp-csharp-connect-sample">пакета SDK</a>
    </td> 
  </tr>
  <tr>
    <td>Xamarin</td>
    <td>
    </td>     
    <td>
        <a href="https://github.com/microsoftgraph/xamarin-csharp-connect-sample">Пример с использованием пакета SDK</a>
    </td> 
  </tr>
</table>

## <a name="see-also"></a>См. также
- Попробуйте примеры вызовов REST в нашем [обозревателе API](https://graph.microsoft.io/graph-explorer).
- [Документация по конечной точке Azure AD](https://azure.microsoft.com/en-us/documentation/services/active-directory/)
- [Документация по конечной точке Azure AD версии 2.0](https://azure.microsoft.com/en-us/documentation/articles/?service=active-directory&term=azure+ad+v2.0)
