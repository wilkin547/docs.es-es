---
title: Controladores de token personalizados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d471e860e74c9a01770c95671401bdbbc23643cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="custom-token-handlers"></a>Controladores de token personalizados
En este tema, se describen los controladores de token en WIF y cómo se usan para procesar tokens. El tema también trata la necesidad de crear controladores personalizados de token para los tipos de token que no se admiten de manera predeterminada en WIF.  
  
## <a name="introduction-to-token-handlers-in-wif"></a>Introducción a los controladores de token en WIF  
 WIF se basa en los controladores de token de seguridad para crear, leer, escribir y para validar los tokens para una aplicación de usuario de confianza (RP) o un servicio de token de seguridad (STS). Los controladores de token son puntos de extensibilidad para agregar un controlador personalizado de token en la canalización de WIF, o para personalizar la manera en que un controlador de token existente administra los tokens. WIF proporciona nueve controladores integrados de token de seguridad que pueden modificarse o reemplazarse completamente para cambiar la función según sea necesario.  
  
## <a name="built-in-security-token-handlers-in-wif"></a>Controladores integrados de token de seguridad en WIF  
 WIF 4.5 incluye nueve clases de controlador de token de seguridad que derivan de la clase base abstracta <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a>Agregar un controlador personalizado de token  
 Algunos tipos de token, como los tokens web simples (SWT) y los tokens web JSON (JWT) no tienen controladores integrados de token proporcionados por WIF. Para estos tipos de token y para otros que no tienen un controlador integrado, debe realizar los pasos siguientes para crear un controlador personalizado de token.  
  
#### <a name="adding-a-custom-token-handler"></a>Agregar un controlador personalizado de token  
  
1.  Cree una clase que derive de <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
2.  Invalide los métodos siguientes y proporcione su propia implementación:  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  Agregue una referencia al nuevo controlador personalizado de token del archivo *Web.config* o *App.config*, dentro de la sección **\<system.identityModel>** que se aplica a WIF. Por ejemplo, el marcado siguiente de configuración especifica un nuevo controlador de token denominado **MyCustomTokenHandler** que reside en el espacio de nombres **CustomToken**.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Observe que si proporciona su propio controlador de token para controlar un tipo de token que ya tiene un controlador integrado de token, necesita agregar un elemento **\<remove>** para quitar el controlador predeterminado y usar su controlador personalizado en su lugar. Por ejemplo, la siguiente configuración reemplaza el elemento <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> predeterminado por el controlador personalizado de token:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789">  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
