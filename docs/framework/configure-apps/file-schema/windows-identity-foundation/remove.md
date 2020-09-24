---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: c4ba7b6f2a9b9092c5f24d424c6de2b0f510ac88
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165005"
---
# \<remove>

<span data-ttu-id="78ddb-101">Quita el controlador de tokens de seguridad especificado de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="78ddb-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="78ddb-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78ddb-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78ddb-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="78ddb-103">Attributes and Elements</span></span>  

 <span data-ttu-id="78ddb-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="78ddb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78ddb-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="78ddb-105">Attributes</span></span>  
  
|<span data-ttu-id="78ddb-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="78ddb-106">Attribute</span></span>|<span data-ttu-id="78ddb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="78ddb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78ddb-108">type</span><span class="sxs-lookup"><span data-stu-id="78ddb-108">type</span></span>|<span data-ttu-id="78ddb-109">Nombre del tipo de CLR del controlador de token que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="78ddb-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="78ddb-110">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="78ddb-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="78ddb-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="78ddb-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78ddb-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="78ddb-112">Child Elements</span></span>  

 <span data-ttu-id="78ddb-113">None</span><span class="sxs-lookup"><span data-stu-id="78ddb-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78ddb-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="78ddb-114">Parent Elements</span></span>  
  
|<span data-ttu-id="78ddb-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="78ddb-115">Element</span></span>|<span data-ttu-id="78ddb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="78ddb-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="78ddb-117">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="78ddb-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="78ddb-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78ddb-118">Example</span></span>  

 <span data-ttu-id="78ddb-119">El siguiente XML muestra el uso de los `<add>` `<remove>` elementos y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="78ddb-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="78ddb-120">El XML se toma del `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78ddb-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
