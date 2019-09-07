---
title: <dataContractSerializer>de < System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398078"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="20f77-102">\<dataContractSerializer > de \<System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="20f77-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="20f77-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="20f77-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="20f77-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="20f77-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="20f77-105">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="20f77-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="20f77-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> dataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="20f77-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f77-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20f77-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20f77-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20f77-108">Attributes and Elements</span></span>  
 <span data-ttu-id="20f77-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20f77-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20f77-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="20f77-110">Attributes</span></span>  
  
|<span data-ttu-id="20f77-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="20f77-111">Element</span></span>|<span data-ttu-id="20f77-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="20f77-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20f77-113">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="20f77-113">ignoreExtensionDataObject</span></span>|<span data-ttu-id="20f77-114">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="20f77-114">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="20f77-115">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="20f77-115">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="20f77-116">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="20f77-116">maxItemsInObjectGraph</span></span>|<span data-ttu-id="20f77-117">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="20f77-117">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="20f77-118">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="20f77-118">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20f77-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20f77-119">Child Elements</span></span>  
  
|<span data-ttu-id="20f77-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="20f77-120">Element</span></span>|<span data-ttu-id="20f77-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="20f77-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20f77-122">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="20f77-122">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="20f77-123">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="20f77-123">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="20f77-124">Para obtener más información sobre los contratos de datos y los tipos conocidos, consulte [Data Contract known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="20f77-124">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20f77-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20f77-125">Parent Elements</span></span>  
  
|<span data-ttu-id="20f77-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="20f77-126">Element</span></span>|<span data-ttu-id="20f77-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="20f77-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20f77-128">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="20f77-128">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="20f77-129">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="20f77-129">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20f77-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20f77-130">Remarks</span></span>  
 <span data-ttu-id="20f77-131">Para obtener más información sobre los tipos conocidos <xref:System.Runtime.Serialization.DataContractSerializer> , vea y [tipos conocidos del contrato de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="20f77-131">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f77-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="20f77-132">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="20f77-133">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="20f77-133">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
