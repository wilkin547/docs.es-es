---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dfea0b0eb4b133308f10b523a659cc00f87252b8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755082"
---
# <a name="ltremovegt"></a><span data-ttu-id="9c468-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="9c468-102">&lt;remove&gt;</span></span>
<span data-ttu-id="9c468-103">Quita el controlador de token de seguridad especificado de la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="9c468-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="9c468-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9c468-104">\<system.identityModel></span></span>  
<span data-ttu-id="9c468-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9c468-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9c468-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="9c468-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="9c468-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="9c468-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c468-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c468-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c468-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c468-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9c468-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c468-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c468-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c468-111">Attributes</span></span>  
  
|<span data-ttu-id="9c468-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9c468-112">Attribute</span></span>|<span data-ttu-id="9c468-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c468-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c468-114">type</span><span class="sxs-lookup"><span data-stu-id="9c468-114">type</span></span>|<span data-ttu-id="9c468-115">El nombre del tipo CLR del controlador de token va a quitar.</span><span class="sxs-lookup"><span data-stu-id="9c468-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="9c468-116">Para obtener más información sobre cómo especificar el `type` de atributo, vea [las referencias de tipos personalizado](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="9c468-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="9c468-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="9c468-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c468-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c468-118">Child Elements</span></span>  
 <span data-ttu-id="9c468-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9c468-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c468-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c468-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9c468-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c468-121">Element</span></span>|<span data-ttu-id="9c468-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c468-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c468-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="9c468-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="9c468-124">Especifica una colección de controladores de tokens de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9c468-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9c468-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c468-125">Example</span></span>  
 <span data-ttu-id="9c468-126">El siguiente XML muestra el uso de la `<add>` y `<remove>` elementos para reemplazar el controlador de token de sesión de forma predeterminada con un controlador de token de sesión personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9c468-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="9c468-127">El XML procede de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9c468-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
