---
title: "C&#243;mo: crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# C&#243;mo: crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF
## Se aplica a  
  
-   Base \(WIF\) de identidad de Microsoft® Windows®  
  
-   Formularios Web Forms de ASP.NET®  
  
## Resumen  
 En este procedimiento proporciona los procedimientos paso a paso detallados para crear la aplicación demanda\- reconozca simple de formularios Web Forms de ASP.NET.  También proporciona instrucciones sobre cómo probar la aplicación demanda\- reconozca simple de formularios Web Forms de ASP.NET para la implementación correcta de autenticación federada.  En este procedimiento no tiene instrucciones detalladas para crear un Servicio de token de seguridad \(STS\), y las supone que ha configurado un STS.  
  
## Contenido  
  
-   Objetivos  
  
-   Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- aplicación de formularios Web Forms de Configurar ASP.NET para la autenticación Demanda\- Basada  
  
-   Paso 3 \- pruebe la solución  
  
## Objetivos  
  
-   Configure la aplicación de formularios Web Forms de ASP.NET para la autenticación demanda\- basada  
  
-   Pruebe la aplicación demanda\- reconozca correcta de formularios Web Forms de ASP.NET  
  
## Resumen de pasos  
  
-   Paso 1 \- cree la aplicación sencilla de formularios Web Forms de ASP.NET  
  
-   Paso 2 \- aplicación de formularios Web Forms de Configurar ASP.NET para la autenticación de Federated  
  
-   Paso 3 \- pruebe la solución  
  
## Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
 En este paso, creará una nueva aplicación de formularios Web Forms de ASP.NET.  
  
#### Para crear una aplicación ASP.NET simple  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo**y, a continuación **Proyecto**.  
  
2.  En la ventana de **Nuevo proyecto** , haga clic en **Aplicación de formularios Web Forms de ASP.NET**.  
  
3.  En **Nombre**, entre en `TestApp` y presione **Aceptar**.  
  
## Paso 2 \- aplicación de formularios Web Forms de Configurar ASP.NET para la autenticación Demanda\- Basada  
 En este paso se agregará entradas de configuración *al archivo de configuración Web.config* de la aplicación de formularios Web Forms de ASP.NET para facilitar demanda\- monitores.  
  
#### Para configurar la aplicación de ASP.NET para la autenticación demanda\-basada  
  
1.  Agregue las siguientes entradas de la sección de configuración *al archivo de configuración Web.config* inmediatamente después del elemento que abre de **\*\*\* \<configuration\> \*\*\*** :  
  
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
  
4.  Agregue un elemento de **\<system.webServer\>** que definir módulos para la autenticación federada.  Observe que el atributo *PublicKeyToken* debe coincidir con el atributo *PublicKeyToken* para las entradas de **\<configSections\>** agregó anteriormente:  
  
    ```  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  Agregue las entradas relacionadas base siguiente de la configuración de la identidad de Windows y asegúrese de que la dirección URL de la aplicación ASP.NET y coincidencia del número de puerto los valores en la entrada de **\<audienceUris\>** , el atributo de **dominio kerberos** de elemento de **\<wsFederation\>** , y el atributo de **respuesta** de elemento de **\<wsFederation\>** .  Asegúrese también de que el valor de **\*\*\* el emisor \*\*\*** ajusta su dirección URL de \(STS\) del Servicio de token de seguridad.  
  
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
  
6.  Agregue la referencia al ensamblado de [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) .  
  
7.  Compile la solución para asegurarse de que hay errores.  
  
## Paso 3 \- pruebe la solución  
 En este paso probará la aplicación de formularios Web Forms de ASP.NET configurada para la autenticación demanda\- basada en.  Para realizar una prueba básica, agregará código que muestra peticiones en el token emitido por el Servicio de token de seguridad \(STS\).  
  
#### Para probar la aplicación web form de ASP.NET para la autenticación demanda\- basada  
  
1.  Abra el archivo de **Default.aspx** bajo el proyecto de **TestApp** y reemplace el marcado existente con el marcado siguiente:  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
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
  
2.  Guarde **Default.aspx**, y vuelva a abrir el código subyacente de **Default.aspx.cs**denominado archivo.  
  
    > [!NOTE]
    >  **Default.aspx.cs** se puede ocultar debajo de **Default.aspx** en el explorador de soluciones.  Si **Default.aspx.cs** no está visible, expanda **Default.aspx** haciendo clic en el triángulo adyacente.  
  
3.  Reemplace la existencia codificada en el método de **Page\_Load** de **Default.aspx.cs** con el código siguiente:  
  
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
  
4.  Guarde **Default.aspx.cs**, compile la solución.  
  
5.  Ejecute la solución presionando la tecla de **F5** .  
  
6.  Se debe mostrar en la página que muestra las peticiones en el token que se ha emitido por el Servicio de token de seguridad.