---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152975"
---
# \<system.runtime.serialization>
<span data-ttu-id="329bc-102">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="329bc-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="329bc-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="329bc-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="329bc-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="329bc-104">Attributes and Elements</span></span>  
 <span data-ttu-id="329bc-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="329bc-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="329bc-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="329bc-106">Attributes</span></span>  
 <span data-ttu-id="329bc-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="329bc-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="329bc-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="329bc-108">Child Elements</span></span>  
  
|<span data-ttu-id="329bc-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="329bc-109">Element</span></span>|<span data-ttu-id="329bc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="329bc-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="329bc-111">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="329bc-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="329bc-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="329bc-112">Parent Elements</span></span>  
  
|<span data-ttu-id="329bc-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="329bc-113">Element</span></span>|<span data-ttu-id="329bc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="329bc-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="329bc-115">\<configuration>Element</span><span class="sxs-lookup"><span data-stu-id="329bc-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="329bc-116">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="329bc-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="329bc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="329bc-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="329bc-118">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="329bc-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="329bc-119">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="329bc-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
