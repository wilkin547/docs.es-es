---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942580"
---
# <a name="remove"></a><span data-ttu-id="03bd1-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="03bd1-101">\<remove></span></span>
<span data-ttu-id="03bd1-102">Quita el controlador de tokens de seguridad especificado de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="03bd1-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="03bd1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="03bd1-103">\<system.identityModel></span></span>  
<span data-ttu-id="03bd1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="03bd1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="03bd1-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="03bd1-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="03bd1-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="03bd1-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03bd1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03bd1-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03bd1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03bd1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03bd1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03bd1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03bd1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="03bd1-110">Attributes</span></span>  
  
|<span data-ttu-id="03bd1-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="03bd1-111">Attribute</span></span>|<span data-ttu-id="03bd1-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="03bd1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03bd1-113">type</span><span class="sxs-lookup"><span data-stu-id="03bd1-113">type</span></span>|<span data-ttu-id="03bd1-114">Nombre del tipo de CLR del controlador de token que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="03bd1-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="03bd1-115">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="03bd1-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="03bd1-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="03bd1-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03bd1-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03bd1-117">Child Elements</span></span>  
 <span data-ttu-id="03bd1-118">None</span><span class="sxs-lookup"><span data-stu-id="03bd1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03bd1-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03bd1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="03bd1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="03bd1-120">Element</span></span>|<span data-ttu-id="03bd1-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="03bd1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03bd1-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="03bd1-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="03bd1-123">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="03bd1-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03bd1-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03bd1-124">Example</span></span>  
 <span data-ttu-id="03bd1-125">El siguiente XML muestra el uso de los `<add>` elementos `<remove>` y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="03bd1-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="03bd1-126">El XML se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03bd1-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
