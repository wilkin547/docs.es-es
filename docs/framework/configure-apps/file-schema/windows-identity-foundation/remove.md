---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793892"
---
# <a name="remove"></a><span data-ttu-id="ca270-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="ca270-101">\<remove></span></span>
<span data-ttu-id="ca270-102">Quita el controlador de token de seguridad especificado de la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="ca270-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="ca270-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ca270-103">\<system.identityModel></span></span>  
<span data-ttu-id="ca270-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ca270-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ca270-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ca270-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ca270-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="ca270-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca270-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca270-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca270-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca270-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ca270-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca270-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca270-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca270-110">Attributes</span></span>  
  
|<span data-ttu-id="ca270-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="ca270-111">Attribute</span></span>|<span data-ttu-id="ca270-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca270-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca270-113">type</span><span class="sxs-lookup"><span data-stu-id="ca270-113">type</span></span>|<span data-ttu-id="ca270-114">El nombre del tipo CLR del controlador de token que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="ca270-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="ca270-115">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="ca270-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="ca270-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ca270-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca270-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca270-117">Child Elements</span></span>  
 <span data-ttu-id="ca270-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ca270-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca270-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca270-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ca270-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca270-120">Element</span></span>|<span data-ttu-id="ca270-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca270-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca270-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ca270-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="ca270-123">Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca270-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ca270-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca270-124">Example</span></span>  
 <span data-ttu-id="ca270-125">El siguiente XML muestra el uso de la `<add>` y `<remove>` elementos que se va a reemplazar el controlador de token de sesión de forma predeterminada con un controlador de token de sesión personalizada.</span><span class="sxs-lookup"><span data-stu-id="ca270-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="ca270-126">El XML procede de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca270-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
