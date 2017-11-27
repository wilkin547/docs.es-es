---
title: '&lt;dataContractSerializer&gt; de &lt;system.runtime.serialization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0c8d0e82696935a480935ebbb71530e052f8d8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltdatacontractserializergt-of-ltsystemruntimeserializationgt"></a><span data-ttu-id="57bf2-102">&lt;dataContractSerializer&gt; de &lt;system.runtime.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="57bf2-102">&lt;dataContractSerializer&gt; of &lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="57bf2-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="57bf2-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="57bf2-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="57bf2-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="57bf2-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="57bf2-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57bf2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57bf2-106">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
            maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String">  
          <knownType type="String">  
             <parameter index="Integer"  
                        type="String" />  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57bf2-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="57bf2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="57bf2-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="57bf2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57bf2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="57bf2-109">Attributes</span></span>  
  
|<span data-ttu-id="57bf2-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="57bf2-110">Element</span></span>|<span data-ttu-id="57bf2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bf2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57bf2-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="57bf2-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="57bf2-113">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="57bf2-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="57bf2-114">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="57bf2-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="57bf2-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="57bf2-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="57bf2-116">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="57bf2-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="57bf2-117">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="57bf2-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57bf2-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="57bf2-118">Child Elements</span></span>  
  
|<span data-ttu-id="57bf2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="57bf2-119">Element</span></span>|<span data-ttu-id="57bf2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bf2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57bf2-121">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="57bf2-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="57bf2-122">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="57bf2-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="57bf2-123">Para obtener más información acerca de los contratos de datos y los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="57bf2-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57bf2-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="57bf2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="57bf2-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="57bf2-125">Element</span></span>|<span data-ttu-id="57bf2-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bf2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57bf2-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="57bf2-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="57bf2-128">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="57bf2-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57bf2-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57bf2-129">Remarks</span></span>  
 <span data-ttu-id="57bf2-130">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer> y [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="57bf2-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bf2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="57bf2-131">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 [<span data-ttu-id="57bf2-132">Los tipos conocidos de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="57bf2-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
