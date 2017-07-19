---
title: "C&#243;mo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# C&#243;mo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF
## Se aplica a  
  
-   Base \(WIF\) de identidad de Microsoft® Windows®  
  
-   ASP.NET® MVC  
  
## Resumen  
 En este procedimiento proporciona los procedimientos paso a paso detallados para crear la aplicación Web demanda\- reconozca simple de ASP.NET MVC.  También proporciona instrucciones cómo probar la aplicación Web demanda\- reconozca simple de ASP.NET MVC para la implementación correcta de la autenticación demanda\- basada en.  En este procedimiento no tiene instrucciones detalladas para crear un Servicio de token de seguridad \(STS\), y las supone que ha configurado un STS.  
  
## Contenido  
  
-   Objetivos  
  
-   Resumen de pasos  
  
-   Paso 1 \- cree la aplicación sencilla de ASP.NET MVC  
  
-   Paso 2 \- aplicación de Configurar ASP.NET MVC para la autenticación Demanda\- Basada  
  
-   Paso 3 \- pruebe la solución  
  
-   Elementos relacionados  
  
## Objetivos  
  
-   Configure la aplicación Web de ASP.NET MVC para la autenticación demanda\-basada  
  
-   Pruebe la aplicación Web demanda\- reconozca correcta de ASP.NET MVC  
  
## Resumen de pasos  
  
-   Paso 1 \- cree la aplicación sencilla de ASP.NET MVC  
  
-   Paso 2 \- aplicación de Configurar ASP.NET MVC para la autenticación Demanda\- Basada  
  
-   Paso 3 \- pruebe la solución  
  
## Paso 1 \- cree la aplicación sencilla de ASP.NET MVC  
 En este paso, creará una nueva aplicación de ASP.NET MVC.  
  
#### Para crear la aplicación sencilla de ASP.NET MVC  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo**y, a continuación **Proyecto**.  
  
2.  En la ventana de **Nuevo proyecto** , haga clic en **Aplicación web de ASP.NET MVC 3**.  
  
3.  En **Nombre**, entre en `TestApp` y presione **Aceptar**.  
  
4.  En el cuadro de diálogo **Nuevo proyecto de ASP.NET MVC 3** , **Aplicación de Internet** seleccione de las plantillas disponibles, asegúrese **Motor de vistas** se establece en **\*\*\* Sintaxis razor \*\*\***, y haga clic en **Aceptar**.  
  
5.  Cuando se abre el proyecto nuevo, haga clic con el botón secundario en el proyecto de **\*\*\* TestApp \*\*\*** en **Explorador de soluciones** y seleccione la opción de **Propiedades** .  
  
6.  En la página de propiedades del proyecto, haga clic en la pestaña de **Web** a la izquierda y asegúrese de que la opción de **Usar servidor web de IIS local** está activada.  
  
## Paso 2 \- aplicación de Configurar ASP.NET MVC para la autenticación Demanda\- Basada  
 En este paso se agregará entradas de configuración *al archivo de configuración Web.config* de la aplicación Web de ASP.NET MVC para facilitar demanda\- monitores.  
  
#### Para configurar la aplicación de ASP.NET MVC para la autenticación demanda\-basada  
  
1.  Agregue las definiciones de sección de configuración siguientes al *archivo de configuración Web.config* .  Éstos definen las secciones de configuración requeridas por la base de la identidad de Windows.  Agregue las definiciones inmediatamente después del elemento que abre de **\*\*\* \<configuration\> \*\*\*** :  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Agregue un elemento de **\<location\>** que habilita el acceso a los metadatos de la federación de la aplicación:  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  Agregue las siguientes entradas de configuración dentro de los elementos de **\<system.web\>** denegar a usuarios, deshabilite la autenticación nativa, y permite a WIF para administrar la autenticación.  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Agregue las entradas relacionadas base siguiente de la configuración de la identidad de Windows y asegúrese de que la dirección URL de la aplicación ASP.NET y coincidencia del número de puerto los valores en la entrada de **\<audienceUris\>** , el atributo de **dominio kerberos** de elemento de **\<wsFederation\>** , y el atributo de **respuesta** de elemento de **\<wsFederation\>** .  Asegúrese también de que el valor de **\*\*\* el emisor \*\*\*** ajusta su dirección URL de \(STS\) del Servicio de token de seguridad.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
5.  Agregue la referencia al ensamblado de [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) .  
  
6.  Compile la solución para asegurarse de que hay errores.  
  
## Paso 3 \- pruebe la solución  
 En este paso probará su aplicación Web ASP.NET MVC configurada para la autenticación demanda\- basada en.  Para realizar la prueba básica agregará código simple que muestra peticiones en el token emitido por el Servicio de token de seguridad \(STS\).  
  
#### Para probar la aplicación ASP.NET MVC para la autenticación demanda\- basada  
  
1.  En **Explorador de soluciones**, expanda la carpeta de **Controladores** y abra *el archivo de HomeController.cs* en el editor.  Agregue el código siguiente al método de **Índice** :  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
  
    ```  
  
2.  En **Explorador de soluciones** expanda las carpetas de **Vistas** y de **Inicio** y *archivo* abierto de Index.cshtml en el editor.  Elimine su contenido y agregue el siguiente marcado:  
  
    ```html  
  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
  
    ```  
  
3.  Ejecute la solución presionando la tecla de **F5** .  
  
4.  Se debe mostrar en la página que muestra las peticiones en el token que se ha emitido por el Servicio de token de seguridad.  
  
## Elementos relacionados  
  
-   [Cómo: crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)