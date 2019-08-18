---
title: <add> de <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 32eff2e7bfdf1aee4c7d37a0e06166afba3cb398
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566733"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="b1955-102">\<Agregar > de \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="b1955-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="b1955-103">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b1955-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="b1955-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b1955-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b1955-105">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="b1955-105">\<routing></span></span>  
<span data-ttu-id="b1955-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="b1955-106">\<namespaceTable></span></span>  
<span data-ttu-id="b1955-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b1955-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1955-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1955-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1955-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b1955-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1955-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b1955-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1955-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b1955-111">Attributes</span></span>  
  
|<span data-ttu-id="b1955-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b1955-112">Attribute</span></span>|<span data-ttu-id="b1955-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b1955-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1955-114">namespace</span><span class="sxs-lookup"><span data-stu-id="b1955-114">namespace</span></span>|<span data-ttu-id="b1955-115">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b1955-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="b1955-116">prefix</span><span class="sxs-lookup"><span data-stu-id="b1955-116">prefix</span></span>|<span data-ttu-id="b1955-117">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b1955-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1955-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b1955-118">Child Elements</span></span>  
 <span data-ttu-id="b1955-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b1955-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1955-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b1955-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b1955-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1955-121">Element</span></span>|<span data-ttu-id="b1955-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b1955-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1955-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="b1955-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="b1955-124">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b1955-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1955-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1955-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
