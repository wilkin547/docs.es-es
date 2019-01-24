---
title: '&lt;add&gt; de &lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 1d3b61fa6653b3910e65b95fa96fd0657e72bf7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632916"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="93a4e-102">&lt;add&gt; de &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="93a4e-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="93a4e-103">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="93a4e-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="93a4e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="93a4e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="93a4e-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="93a4e-105">\<routing></span></span>  
<span data-ttu-id="93a4e-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="93a4e-106">\<namespaceTable></span></span>  
<span data-ttu-id="93a4e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="93a4e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a4e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93a4e-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93a4e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93a4e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="93a4e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93a4e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93a4e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="93a4e-111">Attributes</span></span>  
  
|<span data-ttu-id="93a4e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="93a4e-112">Attribute</span></span>|<span data-ttu-id="93a4e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="93a4e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93a4e-114">namespace</span><span class="sxs-lookup"><span data-stu-id="93a4e-114">namespace</span></span>|<span data-ttu-id="93a4e-115">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="93a4e-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="93a4e-116">prefix</span><span class="sxs-lookup"><span data-stu-id="93a4e-116">prefix</span></span>|<span data-ttu-id="93a4e-117">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="93a4e-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93a4e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93a4e-118">Child Elements</span></span>  
 <span data-ttu-id="93a4e-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="93a4e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93a4e-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93a4e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="93a4e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="93a4e-121">Element</span></span>|<span data-ttu-id="93a4e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="93a4e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93a4e-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="93a4e-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="93a4e-124">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="93a4e-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93a4e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="93a4e-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
