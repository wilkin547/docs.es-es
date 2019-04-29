---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c34eba2614a354f1753d8da077f8653f2c260a97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757916"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="f0c3b-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="f0c3b-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="f0c3b-103">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f0c3b-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f0c3b-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="f0c3b-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0c3b-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0c3b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0c3b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f0c3b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0c3b-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0c3b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0c3b-108">Attributes</span></span>  
 <span data-ttu-id="f0c3b-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f0c3b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f0c3b-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0c3b-110">Child Elements</span></span>  
  
|<span data-ttu-id="f0c3b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0c3b-111">Element</span></span>|<span data-ttu-id="f0c3b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0c3b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0c3b-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="f0c3b-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="f0c3b-114">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="f0c3b-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0c3b-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0c3b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f0c3b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0c3b-116">Element</span></span>|<span data-ttu-id="f0c3b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0c3b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0c3b-118">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="f0c3b-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="f0c3b-119">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="f0c3b-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0c3b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0c3b-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="f0c3b-121">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="f0c3b-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="f0c3b-122">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="f0c3b-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
