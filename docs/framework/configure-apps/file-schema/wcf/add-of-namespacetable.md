---
title: <add> de <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850394"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="6ad82-102">\<add> de \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="6ad82-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="6ad82-103">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6ad82-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="6ad82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ad82-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ad82-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ad82-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6ad82-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ad82-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ad82-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ad82-107">Attributes</span></span>  
  
|<span data-ttu-id="6ad82-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ad82-108">Attribute</span></span>|<span data-ttu-id="6ad82-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ad82-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ad82-110">espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6ad82-110">namespace</span></span>|<span data-ttu-id="6ad82-111">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6ad82-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="6ad82-112">prefix</span><span class="sxs-lookup"><span data-stu-id="6ad82-112">prefix</span></span>|<span data-ttu-id="6ad82-113">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6ad82-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ad82-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ad82-114">Child Elements</span></span>  
 <span data-ttu-id="6ad82-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ad82-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ad82-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ad82-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6ad82-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ad82-117">Element</span></span>|<span data-ttu-id="6ad82-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ad82-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="6ad82-119">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6ad82-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ad82-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ad82-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
