---
title: "Controladores de token personalizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Controladores de token personalizados
Este tema describe los controladores de token en WIF y cómo se utilizan para procesar tokenes.  El tema también trata qué es necesario crear controladores personalizados de token para los tipos de token que no se admiten de forma predeterminada en WIF.  
  
## Introducción a los controladores de token en WIF  
 WIF se basa en los controladores de token de seguridad para crear, leer, escribir, y para validar los tokenes para una aplicación o un servicio \(STS\) de \(RP\) de usuario de confianza de token de seguridad.  Los controladores de token son puntos de extensibilidad para agregar un controlador personalizado del token de la canalización de WIF, o personalizar la manera en que un controlador de token administra tokenes.  WIF proporciona nueve controladores integrados de token de seguridad que pueden modificar o reemplazar completamente para cambiar la funcionalidad según sea necesario.  
  
## Controladores integrados de token de seguridad en WIF  
 WIF 4,5 incluye nueve clases de controlador de token de seguridad que derivan de la clase base abstracta <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## Agregar un controlador personalizado de token  
 Algunos tipos de token, como tokenes web \(SWT\) sencillo y tokenes web \(JWT\) JSON no tienen controladores integrados de token proporcionados por WIF.  Para estos tipos de token y para otros que no tienen un controlador integrado, debe realizar los pasos siguientes para crear un controlador personalizado del token.  
  
#### Agregar un controlador personalizado de token  
  
1.  Cree una nueva clase que derive de <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
2.  Invalide los métodos siguientes y proporcionar su propia implementación:  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  Agregue una referencia al nuevo controlador personalizado del token del *archivo Web.config o* el App.configfile *,* dentro de la sección de **\<system.identityModel\>** que aplica a WIF.  Por ejemplo, el marcado siguiente de configuración especifica un nuevo controlador de token denominado **MyCustomTokenHandler** que reside en el espacio de nombres de **CustomToken** .  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Observe que si se proporciona su propio controlador de token para controlar un token con tipo que ya tiene un controlador integrado de token, necesita agregar un elemento de **\<remove\>** para quitar el controlador predeterminado y utilizar al controlador personalizado en su lugar.  Por ejemplo, la siguiente configuración reemplaza <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> predeterminado con el controlador personalizado de token:  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type=”System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789”>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```