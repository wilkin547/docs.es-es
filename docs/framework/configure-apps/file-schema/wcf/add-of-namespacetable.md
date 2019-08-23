---
title: <add> de <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e2a2e26099f2d31116e4a89297fc1ac984c480d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920074"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="29f67-102">\<Agregar > de \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="29f67-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="29f67-103">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="29f67-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="29f67-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="29f67-104">\<system.serviceModel></span></span>  
<span data-ttu-id="29f67-105">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="29f67-105">\<routing></span></span>  
<span data-ttu-id="29f67-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="29f67-106">\<namespaceTable></span></span>  
<span data-ttu-id="29f67-107">\<add></span><span class="sxs-lookup"><span data-stu-id="29f67-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f67-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29f67-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29f67-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29f67-109">Attributes and Elements</span></span>  
 <span data-ttu-id="29f67-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29f67-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29f67-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="29f67-111">Attributes</span></span>  
  
|<span data-ttu-id="29f67-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="29f67-112">Attribute</span></span>|<span data-ttu-id="29f67-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29f67-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29f67-114">namespace</span><span class="sxs-lookup"><span data-stu-id="29f67-114">namespace</span></span>|<span data-ttu-id="29f67-115">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="29f67-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="29f67-116">prefix</span><span class="sxs-lookup"><span data-stu-id="29f67-116">prefix</span></span>|<span data-ttu-id="29f67-117">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="29f67-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29f67-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29f67-118">Child Elements</span></span>  
 <span data-ttu-id="29f67-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29f67-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29f67-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29f67-120">Parent Elements</span></span>  
  
|<span data-ttu-id="29f67-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="29f67-121">Element</span></span>|<span data-ttu-id="29f67-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29f67-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29f67-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="29f67-123">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="29f67-124">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="29f67-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29f67-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="29f67-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
