---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251930"
---
# <a name="remove"></a><span data-ttu-id="fc08f-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="fc08f-101">\<remove></span></span>
<span data-ttu-id="fc08f-102">Quita el controlador de tokens de seguridad especificado de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="fc08f-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="fc08f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc08f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc08f-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc08f-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="fc08f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fc08f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="fc08f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="fc08f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="fc08f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**</span><span class="sxs-lookup"><span data-stu-id="fc08f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc08f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc08f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc08f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc08f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fc08f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc08f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc08f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc08f-111">Attributes</span></span>  
  
|<span data-ttu-id="fc08f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc08f-112">Attribute</span></span>|<span data-ttu-id="fc08f-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc08f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc08f-114">type</span><span class="sxs-lookup"><span data-stu-id="fc08f-114">type</span></span>|<span data-ttu-id="fc08f-115">Nombre del tipo de CLR del controlador de token que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="fc08f-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="fc08f-116">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="fc08f-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="fc08f-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="fc08f-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc08f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc08f-118">Child Elements</span></span>  
 <span data-ttu-id="fc08f-119">None</span><span class="sxs-lookup"><span data-stu-id="fc08f-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc08f-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc08f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fc08f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc08f-121">Element</span></span>|<span data-ttu-id="fc08f-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc08f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc08f-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="fc08f-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="fc08f-124">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fc08f-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc08f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc08f-125">Example</span></span>  
 <span data-ttu-id="fc08f-126">El siguiente XML muestra el uso de los `<add>` elementos `<remove>` y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="fc08f-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="fc08f-127">El XML se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fc08f-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
