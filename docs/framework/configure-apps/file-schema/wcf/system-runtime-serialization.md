---
description: 'Más información acerca de: <System. Runtime. Serialization>'
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: cf1d95c8650e4b6979d4f34b0bed1fa395911f2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786634"
---
# \<system.runtime.serialization>

<span data-ttu-id="44fe9-103">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="44fe9-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="44fe9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44fe9-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44fe9-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44fe9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="44fe9-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44fe9-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44fe9-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="44fe9-107">Attributes</span></span>  

 <span data-ttu-id="44fe9-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="44fe9-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44fe9-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44fe9-109">Child Elements</span></span>  
  
|<span data-ttu-id="44fe9-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="44fe9-110">Element</span></span>|<span data-ttu-id="44fe9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="44fe9-111">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="44fe9-112">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="44fe9-112">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44fe9-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44fe9-113">Parent Elements</span></span>  
  
|<span data-ttu-id="44fe9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="44fe9-114">Element</span></span>|<span data-ttu-id="44fe9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="44fe9-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44fe9-116">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="44fe9-116">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="44fe9-117">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="44fe9-117">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44fe9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="44fe9-118">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="44fe9-119">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="44fe9-119">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="44fe9-120">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="44fe9-120">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
