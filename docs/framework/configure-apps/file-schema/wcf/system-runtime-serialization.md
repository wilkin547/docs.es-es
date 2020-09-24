---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 84ced06691ce3b3c9c9573fc9d114335096a849d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157114"
---
# \<system.runtime.serialization>

<span data-ttu-id="14291-102">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="14291-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="14291-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14291-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14291-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14291-104">Attributes and Elements</span></span>  

 <span data-ttu-id="14291-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14291-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14291-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="14291-106">Attributes</span></span>  

 <span data-ttu-id="14291-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="14291-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14291-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14291-108">Child Elements</span></span>  
  
|<span data-ttu-id="14291-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="14291-109">Element</span></span>|<span data-ttu-id="14291-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="14291-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="14291-111">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="14291-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14291-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14291-112">Parent Elements</span></span>  
  
|<span data-ttu-id="14291-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="14291-113">Element</span></span>|<span data-ttu-id="14291-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="14291-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14291-115">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="14291-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="14291-116">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="14291-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14291-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="14291-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="14291-118">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="14291-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="14291-119">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="14291-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
