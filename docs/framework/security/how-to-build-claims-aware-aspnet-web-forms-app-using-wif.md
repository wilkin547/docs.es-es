---
title: Cómo compilar aplicaciones de formularios Web Forms de ASP.NET con reconocimiento de notificaciones mediante WIF
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
ms.openlocfilehash: 45ad084013cbcafdf0d7c4ac3e0fd952305232c4
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851558"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a>Cómo compilar aplicaciones de formularios Web Forms de ASP.NET con reconocimiento de notificaciones mediante WIF
## <a name="applies-to"></a>Se aplica a  
  
- Microsoft® Windows® Identity Foundation (WIF)  
  
- Formularios Web Forms ASP.NET®  
  
## <a name="summary"></a>Resumen  
 Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones. También proporciona instrucciones sobre cómo probar la aplicación sencilla de formularios Web Forms ASP.NET para notificaciones para obtener una implementación correcta de la autenticación federada. Este tema de procedimientos no tiene instrucciones detalladas para crear un Servicio de tokens de seguridad (STS) y presupone que ya ha configurado uno.  
  
## <a name="contents"></a>Contenido  
  
- Objetivos  
  
- Resumen de pasos  
  
- Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
  
- Paso 2: Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones  
  
- Paso 3: Probar la solución  
  
## <a name="objectives"></a>Objetivos  
  
- Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones  
  
- Probar una aplicación de formularios Web Forms ASP.NET para notificaciones correcta  
  
## <a name="summary-of-steps"></a>Resumen de pasos  
  
- Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
  
- Paso 2: Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación federada  
  
- Paso 3: Probar la solución  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
 En este paso creará una aplicación de formularios Web Forms ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Para crear una aplicación de ASP.NET sencilla  
  
1. Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.  
  
2. En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.  
  
3. En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a>Paso 2: Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones  
 En este paso agregará entradas de configuración al archivo de configuración *Web.config* de su aplicación de formularios Web Forms ASP.NET para notificaciones.  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a>Para configurar la aplicación ASP.NET para la autenticación basada en notificaciones  
  
1. Agregue las siguientes entradas de la sección de configuración al archivo de configuración *Web.config* inmediatamente después del elemento de apertura **\<configuration>** :  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2. Agregue un elemento **\<location>** que permita el acceso a los metadatos de federación de la aplicación:  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3. Agregue las siguientes entradas de configuración dentro de los elementos **\<system.web>** para denegar usuarios, deshabilitar la autenticación nativa y habilitar WIF para administrar la autenticación.  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4. Agregue un elemento **\<system.webServer>** que defina los módulos para la autenticación federada. Tenga en cuenta que el atributo *PublicKeyToken* debe ser el mismo que el atributo *PublicKeyToken* para las entradas **\<configSections>** que se han agregado anteriormente:  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5. Agregue las siguientes entradas de configuración relacionadas con Windows Identity Foundation y asegúrese de que su URL de la aplicación ASP.NET y el número de puerto coinciden con los valores de la entrada **\<audienceUris>** , el atributo **realm** del elemento **\<wsFederation>** y el atributo **reply** del elemento **\<wsFederation>** . También asegúrese de que el valor **issuer** se adapta a su URL del servicio de token de seguridad (STS).  
  
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
            <cookieHandler requireSsl="true" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="true" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6. Agregue una referencia al ensamblado <xref:System.IdentityModel>.  
  
7. Compile la solución y asegúrese de que no existan errores.  
  
## <a name="step-3--test-your-solution"></a>Paso 3: Probar la solución  
 En este paso probará la aplicación de formularios Web Forms ASP.NET configurada para la autenticación basada en notificaciones. Para realizar una prueba básica, agregará código que muestra notificaciones en el token emitido mediante el servicio de token de seguridad (STS).  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a>Para probar su aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones  
  
1. Abra el archivo **Default.aspx** en el proyecto **TestApp** y reemplace su marcado existente por el marcado siguiente:  
  
    ```aspx-csharp
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2. Guarde **Default.aspx** y abra su archivo de código subyacente denominado **Default.aspx.cs**.  
  
    > [!NOTE]
    > **Default.aspx.cs** puede estar oculto bajo **Default.aspx** en el Explorador de soluciones. Si **Default.aspx.cs** no está visible, expanda **Default.aspx** haciendo clic en el triángulo que se encuentra al lado.  
  
3. Reemplace el código existente en el método **Page_Load** de **Default.aspx.cs** por el código siguiente:  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4. Guarde **Default.aspx.cs** y compile la solución.  
  
5. Presione la tecla **F5** para ejecutar la solución.  
  
6. Debe estar presente en la página que muestra las notificaciones del token que ha emitido mediante el servicio de token de seguridad.
