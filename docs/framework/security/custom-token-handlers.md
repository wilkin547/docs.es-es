---
title: Controladores de token personalizados
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
ms.openlocfilehash: c27abb5df7f895a9dec5f7f784f1a3ff0b31edb7
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200885"
---
# <a name="custom-token-handlers"></a><span data-ttu-id="40c6d-102">Controladores de token personalizados</span><span class="sxs-lookup"><span data-stu-id="40c6d-102">Custom Token Handlers</span></span>
<span data-ttu-id="40c6d-103">En este tema, se describen los controladores de token en WIF y cómo se usan para procesar tokens.</span><span class="sxs-lookup"><span data-stu-id="40c6d-103">This topic discusses token handlers in WIF and how they are used to process tokens.</span></span> <span data-ttu-id="40c6d-104">El tema también trata la necesidad de crear controladores personalizados de token para los tipos de token que no se admiten de manera predeterminada en WIF.</span><span class="sxs-lookup"><span data-stu-id="40c6d-104">The topic also covers what is necessary to create custom token handlers for token types that are not supported by default in WIF.</span></span>  
  
## <a name="introduction-to-token-handlers-in-wif"></a><span data-ttu-id="40c6d-105">Introducción a los controladores de token en WIF</span><span class="sxs-lookup"><span data-stu-id="40c6d-105">Introduction to Token Handlers in WIF</span></span>  
 <span data-ttu-id="40c6d-106">WIF se basa en los controladores de token de seguridad para crear, leer, escribir y para validar los tokens para una aplicación de usuario de confianza (RP) o un servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="40c6d-106">WIF relies on security token handlers to create, read, write, and validate tokens for a relying party (RP) application or a security token service (STS).</span></span> <span data-ttu-id="40c6d-107">Los controladores de token son puntos de extensibilidad para agregar un controlador personalizado de token en la canalización de WIF, o para personalizar la manera en que un controlador de token existente administra los tokens.</span><span class="sxs-lookup"><span data-stu-id="40c6d-107">Token handlers are extensibility points for you to add a custom token handler in the WIF pipeline, or to customize the way that an existing token handler manages tokens.</span></span> <span data-ttu-id="40c6d-108">WIF proporciona nueve controladores integrados de token de seguridad que pueden modificarse o reemplazarse completamente para cambiar la función según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="40c6d-108">WIF provides nine built-in security token handlers that can be modified or entirely overridden to change the functionality as necessary.</span></span>  
  
## <a name="built-in-security-token-handlers-in-wif"></a><span data-ttu-id="40c6d-109">Controladores integrados de token de seguridad en WIF</span><span class="sxs-lookup"><span data-stu-id="40c6d-109">Built-In Security Token Handlers in WIF</span></span>  
 <span data-ttu-id="40c6d-110">WIF 4.5 incluye nueve clases de controlador de token de seguridad que derivan de la clase base abstracta <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span><span class="sxs-lookup"><span data-stu-id="40c6d-110">WIF 4.5 includes nine security token handler classes that derive from the abstract base class <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span></span>  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a><span data-ttu-id="40c6d-111">Agregar un controlador personalizado de token</span><span class="sxs-lookup"><span data-stu-id="40c6d-111">Adding a Custom Token Handler</span></span>  
 <span data-ttu-id="40c6d-112">Algunos tipos de token, como los tokens web simples (SWT) y los tokens web JSON (JWT) no tienen controladores integrados de token proporcionados por WIF.</span><span class="sxs-lookup"><span data-stu-id="40c6d-112">Some token types, such as Simple Web Tokens (SWT) and JSON Web Tokens (JWT) do not have built-in token handlers provided by WIF.</span></span> <span data-ttu-id="40c6d-113">Para estos tipos de token y para otros que no tienen un controlador integrado, debe realizar los pasos siguientes para crear un controlador personalizado de token.</span><span class="sxs-lookup"><span data-stu-id="40c6d-113">For these token types and for others that do not have a built-in handler, you need to perform the following steps to create a custom token handler.</span></span>  
  
#### <a name="adding-a-custom-token-handler"></a><span data-ttu-id="40c6d-114">Agregar un controlador personalizado de token</span><span class="sxs-lookup"><span data-stu-id="40c6d-114">Adding a custom token handler</span></span>  
  
1.  <span data-ttu-id="40c6d-115">Cree una clase que derive de <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="40c6d-115">Create a new class that derives from <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span></span>  
  
2.  <span data-ttu-id="40c6d-116">Invalide los métodos siguientes y proporcione su propia implementación:</span><span class="sxs-lookup"><span data-stu-id="40c6d-116">Override the following methods and provide your own implementation:</span></span>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  <span data-ttu-id="40c6d-117">Agregue una referencia al nuevo controlador personalizado de token del archivo *Web.config* o *App.config*, dentro de la sección **\<system.identityModel>** que se aplica a WIF.</span><span class="sxs-lookup"><span data-stu-id="40c6d-117">Add a reference to the new custom token handler in the *Web.config* or *App.config* file, within the **\<system.identityModel>** section that applies to WIF.</span></span> <span data-ttu-id="40c6d-118">Por ejemplo, el marcado siguiente de configuración especifica un nuevo controlador de token denominado **MyCustomTokenHandler** que reside en el espacio de nombres **CustomToken**.</span><span class="sxs-lookup"><span data-stu-id="40c6d-118">For example, the following configuration markup specifies a new token handler named **MyCustomTokenHandler** that resides in the **CustomToken** namespace.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     <span data-ttu-id="40c6d-119">Observe que si proporciona su propio controlador de token para controlar un tipo de token que ya tiene un controlador integrado de token, necesita agregar un elemento **\<remove>** para quitar el controlador predeterminado y usar su controlador personalizado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="40c6d-119">Note that if you are providing your own token handler to handle a token type that already has a built-in token handler, you need to add a **\<remove>** element to drop the default handler and use your custom handler instead.</span></span> <span data-ttu-id="40c6d-120">Por ejemplo, la siguiente configuración reemplaza el elemento <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> predeterminado por el controlador personalizado de token:</span><span class="sxs-lookup"><span data-stu-id="40c6d-120">For example, the following configuration replaces the default <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> with the custom token handler:</span></span>  
  
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
