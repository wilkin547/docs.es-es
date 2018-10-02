---
title: 'Cómo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF'
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
ms.openlocfilehash: 4a003acbf4e182a0493368b586a3add229d8b526
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47863031"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a>Cómo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF
## <a name="applies-to"></a>Se aplica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® MVC  
  
## <a name="summary"></a>Resumen  
 Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación web de ASP.NET MVC para notificaciones. También proporciona instrucciones sobre cómo probar la aplicación web sencilla de ASP.NET MVC para notificaciones para obtener una implementación correcta de la autenticación basada en notificaciones. Este tema de procedimientos no tiene instrucciones detalladas para crear un Servicio de tokens de seguridad (STS) y presupone que ya ha configurado uno.  
  
## <a name="contents"></a>Contenido  
  
-   Objetivos  
  
-   Resumen de pasos  
  
-   Paso 1: Crear una aplicación sencilla de ASP.NET MVC  
  
-   Paso 2: Configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones  
  
-   Paso 3: Probar la solución  
  
-   Elementos relacionados  
  
## <a name="objectives"></a>Objetivos  
  
-   Configurar una aplicación web de ASP.NET MVC para la autenticación basada en notificaciones  
  
-   Probar una aplicación web de ASP.NET MVC para notificaciones correcta  
  
## <a name="summary-of-steps"></a>Resumen de pasos  
  
-   Paso 1: Crear una aplicación sencilla de ASP.NET MVC  
  
-   Paso 2: Configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones  
  
-   Paso 3: Probar la solución  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a>Paso 1: Crear una aplicación sencilla de ASP.NET MVC  
 En este paso se crea una aplicación de ASP.NET MVC.  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a>Para crear una aplicación sencilla de ASP.NET MVC  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.  
  
2.  En la ventana **Nuevo proyecto**, haga clic en **Aplicación web de ASP.NET MVC 3**.  
  
3.  En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.  
  
4.  En el cuadro de diálogo **Nuevo proyecto de ASP.NET MVC 3**, seleccione **Aplicación de Internet** de las plantillas disponibles; asegúrese de que **Motor de vista** se establece en **Razor** y, después, haga clic en **Aceptar**.  
  
5.  Cuando se abre el nuevo proyecto, haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione la opción **Propiedades**.  
  
6.  En la página de propiedades del proyecto, haga clic en la pestaña **Web** situada a la izquierda y asegúrese de que la opción **Usar servidor web de IIS local** está seleccionada.  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a>Paso 2: Configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones  
 En este paso agregará entradas de configuración al archivo de configuración *Web.config* de su aplicación web de ASP.NET MVC para notificaciones.  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a>Para configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones  
  
1.  Agregue las siguientes definiciones de la sección de configuración al archivo de configuración *Web.config*. Estas definen las secciones de configuración necesarias para Windows Identity Foundation. Agregue las definiciones inmediatamente después del elemento de apertura **\<configuration>**:  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Agregue un elemento **\<location>** que permita el acceso a los metadatos de federación de la aplicación:  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  Agregue las siguientes entradas de configuración dentro de los elementos **\<system.web>** para denegar usuarios, deshabilitar la autenticación nativa y habilitar WIF para administrar la autenticación.  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Agregue las siguientes entradas de configuración relacionadas con Windows Identity Foundation y asegúrese de que su URL de la aplicación ASP.NET y el número de puerto coinciden con los valores de la entrada **\<audienceUris>**, el atributo **realm** del elemento **\<wsFederation>** y el atributo **reply** del elemento **\<wsFederation>**. También asegúrese de que el valor **issuer** se adapta a su URL del servicio de token de seguridad (STS).  
  
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
  
5.  Agregue una referencia al ensamblado <xref:System.IdentityModel>.  
  
6.  Compile la solución y asegúrese de que existan errores.  
  
## <a name="step-3--test-your-solution"></a>Paso 3: Probar la solución  
 En este paso probará la aplicación web de ASP.NET MVC configurada para la autenticación basada en notificaciones. Para realizar una prueba básica, agregará código simple que muestra notificaciones en el token emitido mediante el servicio de token de seguridad (STS).  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a>Para probar su aplicación de ASP.NET MVC para la autenticación basada en notificaciones  
  
1.  En el **Explorador de soluciones**, expanda la carpeta **Controladores** y abra el archivo *HomeController.cs* en el editor. Agregue el código siguiente al método **Index**:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  En el **Explorador de soluciones**, expanda **Vistas** y, después, las carpetas **Inicio**, y abra el archivo *Index.cshtml* en el editor. Elimine su contenido y agregue el siguiente marcado:  
  
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
  
3.  Presione la tecla **F5** para ejecutar la solución.  
  
4.  Debe estar presente en la página que muestra las notificaciones del token que ha emitido mediante el servicio de token de seguridad.  
  
## <a name="related-items"></a>Elementos relacionados  
  
-   [Crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
