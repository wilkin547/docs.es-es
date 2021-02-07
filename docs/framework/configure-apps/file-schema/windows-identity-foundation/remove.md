---
description: 'Más información acerca de: <remove>'
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 942148f677e10bbab7b86acfba2d0fdfb1b10ca7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664072"
---
# \<remove>

<span data-ttu-id="8f69d-102">Quita el controlador de tokens de seguridad especificado de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="8f69d-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="8f69d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f69d-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f69d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8f69d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8f69d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8f69d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f69d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8f69d-106">Attributes</span></span>  
  
|<span data-ttu-id="8f69d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="8f69d-107">Attribute</span></span>|<span data-ttu-id="8f69d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f69d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f69d-109">type</span><span class="sxs-lookup"><span data-stu-id="8f69d-109">type</span></span>|<span data-ttu-id="8f69d-110">Nombre del tipo de CLR del controlador de token que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="8f69d-110">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="8f69d-111">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="8f69d-111">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="8f69d-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="8f69d-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f69d-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8f69d-113">Child Elements</span></span>  

 <span data-ttu-id="8f69d-114">None</span><span class="sxs-lookup"><span data-stu-id="8f69d-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f69d-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8f69d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8f69d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f69d-116">Element</span></span>|<span data-ttu-id="8f69d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f69d-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="8f69d-118">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8f69d-118">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8f69d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f69d-119">Example</span></span>  

 <span data-ttu-id="8f69d-120">El siguiente XML muestra el uso de los `<add>` `<remove>` elementos y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="8f69d-120">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="8f69d-121">El XML se toma del `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8f69d-121">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
