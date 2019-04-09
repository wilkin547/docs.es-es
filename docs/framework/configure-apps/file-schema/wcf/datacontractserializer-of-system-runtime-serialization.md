---
title: <dataContractSerializer> de < system.runtime.serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115367"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="13baa-102">\<dataContractSerializer > de \<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="13baa-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="13baa-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="13baa-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="13baa-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="13baa-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="13baa-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="13baa-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13baa-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13baa-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13baa-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13baa-107">Attributes and Elements</span></span>  
 <span data-ttu-id="13baa-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13baa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13baa-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="13baa-109">Attributes</span></span>  
  
|<span data-ttu-id="13baa-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="13baa-110">Element</span></span>|<span data-ttu-id="13baa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="13baa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13baa-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="13baa-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="13baa-113">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="13baa-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="13baa-114">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="13baa-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="13baa-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="13baa-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="13baa-116">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="13baa-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="13baa-117">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="13baa-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13baa-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13baa-118">Child Elements</span></span>  
  
|<span data-ttu-id="13baa-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="13baa-119">Element</span></span>|<span data-ttu-id="13baa-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="13baa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13baa-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="13baa-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="13baa-122">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="13baa-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="13baa-123">Para obtener más información acerca de los contratos de datos y los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="13baa-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13baa-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13baa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="13baa-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="13baa-125">Element</span></span>|<span data-ttu-id="13baa-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="13baa-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13baa-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="13baa-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="13baa-128">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="13baa-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13baa-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13baa-129">Remarks</span></span>  
 <span data-ttu-id="13baa-130">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer> y [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="13baa-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13baa-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="13baa-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="13baa-132">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="13baa-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
