---
description: 'Más información sobre: <dataContractSerializer> de <System. Runtime. serialization>'
title: <dataContractSerializer> de <System. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 3755005782ea773344326d211b9f8f115a97f2ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754425"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="36008-103">\<dataContractSerializer> de \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="36008-103">\<dataContractSerializer> of \<system.runtime.serialization></span></span>

<span data-ttu-id="36008-104">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="36008-104">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="36008-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36008-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36008-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="36008-106">Attributes and Elements</span></span>  

 <span data-ttu-id="36008-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="36008-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36008-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="36008-108">Attributes</span></span>  
  
|<span data-ttu-id="36008-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="36008-109">Element</span></span>|<span data-ttu-id="36008-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="36008-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36008-111">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="36008-111">ignoreExtensionDataObject</span></span>|<span data-ttu-id="36008-112">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="36008-112">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="36008-113">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="36008-113">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="36008-114">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="36008-114">maxItemsInObjectGraph</span></span>|<span data-ttu-id="36008-115">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="36008-115">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="36008-116">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="36008-116">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36008-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="36008-117">Child Elements</span></span>  
  
|<span data-ttu-id="36008-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="36008-118">Element</span></span>|<span data-ttu-id="36008-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="36008-119">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="36008-120">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="36008-120">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="36008-121">Para obtener más información sobre los contratos de datos y los tipos conocidos, consulte [Data Contract known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="36008-121">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36008-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="36008-122">Parent Elements</span></span>  
  
|<span data-ttu-id="36008-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="36008-123">Element</span></span>|<span data-ttu-id="36008-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="36008-124">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="36008-125">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="36008-125">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36008-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36008-126">Remarks</span></span>  

 <span data-ttu-id="36008-127">Para obtener más información sobre los tipos conocidos, vea <xref:System.Runtime.Serialization.DataContractSerializer> y [tipos conocidos del contrato de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="36008-127">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36008-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="36008-128">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="36008-129">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="36008-129">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
