---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 4d3dd9042951ffb46b8e0a3f7bb7bcdee23fd58b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148842"
---
# <a name="knowntype"></a><span data-ttu-id="7fae3-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="7fae3-101">\<knownType></span></span>
<span data-ttu-id="7fae3-102">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="7fae3-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7fae3-103">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="7fae3-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="7fae3-104">Para obtener más información, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="7fae3-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="7fae3-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="7fae3-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="7fae3-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7fae3-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="7fae3-107">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="7fae3-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="7fae3-108">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="7fae3-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="7fae3-109">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="7fae3-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fae3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fae3-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="7fae3-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7fae3-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fae3-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7fae3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7fae3-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7fae3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fae3-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="7fae3-114">Attributes</span></span>  
  
|<span data-ttu-id="7fae3-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="7fae3-115">Attribute</span></span>|<span data-ttu-id="7fae3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fae3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fae3-117">type</span><span class="sxs-lookup"><span data-stu-id="7fae3-117">type</span></span>|<span data-ttu-id="7fae3-118">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="7fae3-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fae3-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7fae3-119">Child Elements</span></span>  
  
|<span data-ttu-id="7fae3-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fae3-120">Element</span></span>|<span data-ttu-id="7fae3-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fae3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fae3-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="7fae3-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="7fae3-123">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="7fae3-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7fae3-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7fae3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7fae3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fae3-125">Element</span></span>|<span data-ttu-id="7fae3-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fae3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fae3-127">\<add></span><span class="sxs-lookup"><span data-stu-id="7fae3-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="7fae3-128">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="7fae3-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fae3-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fae3-129">Remarks</span></span>  
 <span data-ttu-id="7fae3-130">Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7fae3-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7fae3-131">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="7fae3-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fae3-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fae3-132">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="7fae3-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fae3-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7fae3-134">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="7fae3-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="7fae3-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7fae3-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="7fae3-136">\<add></span><span class="sxs-lookup"><span data-stu-id="7fae3-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
