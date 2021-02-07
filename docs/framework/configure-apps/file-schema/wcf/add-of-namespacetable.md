---
description: 'Más información sobre: <add> de <namespaceTable>'
title: <add> de <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: b7804bdec4a1fb2199c81ba0dde031b80b451d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750265"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="3de44-103">\<add> de \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="3de44-103">\<add> of \<namespaceTable></span></span>

<span data-ttu-id="3de44-104">Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3de44-104">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3de44-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3de44-105">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3de44-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3de44-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3de44-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3de44-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3de44-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3de44-108">Attributes</span></span>  
  
|<span data-ttu-id="3de44-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="3de44-109">Attribute</span></span>|<span data-ttu-id="3de44-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3de44-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3de44-111">espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="3de44-111">namespace</span></span>|<span data-ttu-id="3de44-112">Cadena que contiene el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3de44-112">A string containing the namespace.</span></span>|  
|<span data-ttu-id="3de44-113">prefix</span><span class="sxs-lookup"><span data-stu-id="3de44-113">prefix</span></span>|<span data-ttu-id="3de44-114">Cadena que contiene el prefijo para este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3de44-114">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3de44-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3de44-115">Child Elements</span></span>  

 <span data-ttu-id="3de44-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3de44-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3de44-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3de44-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3de44-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3de44-118">Element</span></span>|<span data-ttu-id="3de44-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3de44-119">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="3de44-120">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3de44-120">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3de44-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3de44-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
