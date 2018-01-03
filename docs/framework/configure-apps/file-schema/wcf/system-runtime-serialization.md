---
title: '&lt;System.Runtime.Serialization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab66252ebc5b87c197b3e4ac7b6def9355e5f201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="339e3-102">&lt;System.Runtime.Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="339e3-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="339e3-103">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="339e3-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="339e3-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="339e3-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="339e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="339e3-105">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
             <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="339e3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="339e3-106">Attributes and Elements</span></span>  
 <span data-ttu-id="339e3-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="339e3-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="339e3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="339e3-108">Attributes</span></span>  
 <span data-ttu-id="339e3-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="339e3-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="339e3-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="339e3-110">Child Elements</span></span>  
  
|<span data-ttu-id="339e3-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="339e3-111">Element</span></span>|<span data-ttu-id="339e3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="339e3-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="339e3-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="339e3-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="339e3-114">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="339e3-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="339e3-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="339e3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="339e3-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="339e3-116">Element</span></span>|<span data-ttu-id="339e3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="339e3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="339e3-118">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="339e3-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="339e3-119">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="339e3-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="339e3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="339e3-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="339e3-121">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="339e3-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="339e3-122">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="339e3-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
