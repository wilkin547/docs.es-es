---
title: <dataContractSerializer>de <System. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398078"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="37790-102">\<dataContractSerializer> de \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="37790-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="37790-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="37790-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="37790-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37790-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37790-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37790-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37790-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37790-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37790-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="37790-107">Attributes</span></span>  
  
|<span data-ttu-id="37790-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="37790-108">Element</span></span>|<span data-ttu-id="37790-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="37790-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37790-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="37790-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="37790-111">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="37790-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="37790-112">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="37790-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="37790-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="37790-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="37790-114">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="37790-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="37790-115">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="37790-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37790-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37790-116">Child Elements</span></span>  
  
|<span data-ttu-id="37790-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="37790-117">Element</span></span>|<span data-ttu-id="37790-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="37790-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="37790-119">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="37790-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="37790-120">Para obtener más información sobre los contratos de datos y los tipos conocidos, consulte [Data Contract known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="37790-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37790-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37790-121">Parent Elements</span></span>  
  
|<span data-ttu-id="37790-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="37790-122">Element</span></span>|<span data-ttu-id="37790-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="37790-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="37790-124">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="37790-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37790-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37790-125">Remarks</span></span>  
 <span data-ttu-id="37790-126">Para obtener más información sobre los tipos conocidos, vea <xref:System.Runtime.Serialization.DataContractSerializer> y [tipos conocidos del contrato de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="37790-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37790-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37790-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="37790-128">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="37790-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
