---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152975"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="fa94e-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="fa94e-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="fa94e-103">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="fa94e-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="fa94e-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa94e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa94e-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span><span class="sxs-lookup"><span data-stu-id="fa94e-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa94e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa94e-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa94e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa94e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fa94e-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa94e-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa94e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa94e-109">Attributes</span></span>  
 <span data-ttu-id="fa94e-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa94e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa94e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa94e-111">Child Elements</span></span>  
  
|<span data-ttu-id="fa94e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa94e-112">Element</span></span>|<span data-ttu-id="fa94e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa94e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa94e-114">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="fa94e-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="fa94e-115">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="fa94e-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa94e-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa94e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fa94e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa94e-117">Element</span></span>|<span data-ttu-id="fa94e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa94e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa94e-119">\<configuración> Elemento</span><span class="sxs-lookup"><span data-stu-id="fa94e-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="fa94e-120">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="fa94e-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa94e-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa94e-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="fa94e-122">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="fa94e-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="fa94e-123">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="fa94e-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
