---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c34eba2614a354f1753d8da077f8653f2c260a97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165898"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="2b941-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2b941-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="2b941-103">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2b941-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="2b941-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="2b941-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b941-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b941-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b941-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2b941-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2b941-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2b941-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b941-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b941-108">Attributes</span></span>  
 <span data-ttu-id="2b941-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2b941-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b941-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2b941-110">Child Elements</span></span>  
  
|<span data-ttu-id="2b941-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b941-111">Element</span></span>|<span data-ttu-id="2b941-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b941-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b941-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2b941-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="2b941-114">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="2b941-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b941-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2b941-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2b941-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b941-116">Element</span></span>|<span data-ttu-id="2b941-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b941-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b941-118">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="2b941-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="2b941-119">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="2b941-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b941-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b941-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="2b941-121">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="2b941-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="2b941-122">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="2b941-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
