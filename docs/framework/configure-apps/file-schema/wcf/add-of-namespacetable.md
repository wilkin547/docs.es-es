---
title: <add> de <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850394"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="5d406-102">\<Agregar > de \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="5d406-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="5d406-103">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5d406-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="5d406-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d406-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d406-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d406-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d406-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="5d406-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="5d406-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> namespaceTable**](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="5d406-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="5d406-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="5d406-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d406-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d406-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d406-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d406-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d406-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d406-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d406-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d406-112">Attributes</span></span>  
  
|<span data-ttu-id="5d406-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d406-113">Attribute</span></span>|<span data-ttu-id="5d406-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d406-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d406-115">namespace</span><span class="sxs-lookup"><span data-stu-id="5d406-115">namespace</span></span>|<span data-ttu-id="5d406-116">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5d406-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="5d406-117">prefix</span><span class="sxs-lookup"><span data-stu-id="5d406-117">prefix</span></span>|<span data-ttu-id="5d406-118">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5d406-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d406-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d406-119">Child Elements</span></span>  
 <span data-ttu-id="5d406-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d406-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d406-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d406-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5d406-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d406-122">Element</span></span>|<span data-ttu-id="5d406-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d406-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d406-124">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="5d406-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="5d406-125">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5d406-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d406-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d406-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
