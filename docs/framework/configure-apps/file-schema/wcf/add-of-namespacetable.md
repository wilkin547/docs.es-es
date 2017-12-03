---
title: '&lt;add&gt; de &lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f159e3d92fdc7443cd20cf88300f331b78273ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="30790-102">&lt;add&gt; de &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="30790-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="30790-103">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="30790-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="30790-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="30790-104">\<system.serviceModel></span></span>  
<span data-ttu-id="30790-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="30790-105">\<routing></span></span>  
<span data-ttu-id="30790-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="30790-106">\<namespaceTable></span></span>  
<span data-ttu-id="30790-107">\<add></span><span class="sxs-lookup"><span data-stu-id="30790-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30790-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30790-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30790-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="30790-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30790-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="30790-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30790-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="30790-111">Attributes</span></span>  
  
|<span data-ttu-id="30790-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="30790-112">Attribute</span></span>|<span data-ttu-id="30790-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="30790-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30790-114">namespace</span><span class="sxs-lookup"><span data-stu-id="30790-114">namespace</span></span>|<span data-ttu-id="30790-115">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="30790-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="30790-116">prefix</span><span class="sxs-lookup"><span data-stu-id="30790-116">prefix</span></span>|<span data-ttu-id="30790-117">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="30790-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30790-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="30790-118">Child Elements</span></span>  
 <span data-ttu-id="30790-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="30790-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30790-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="30790-120">Parent Elements</span></span>  
  
|<span data-ttu-id="30790-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="30790-121">Element</span></span>|<span data-ttu-id="30790-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="30790-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30790-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="30790-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="30790-124">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="30790-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30790-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="30790-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
