---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 4d3dd9042951ffb46b8e0a3f7bb7bcdee23fd58b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148842"
---
# <a name="knowntype"></a><span data-ttu-id="69a72-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="69a72-101">\<knownType></span></span>
<span data-ttu-id="69a72-102">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="69a72-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="69a72-103">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="69a72-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="69a72-104">Para obtener más información, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="69a72-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="69a72-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="69a72-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="69a72-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="69a72-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="69a72-107">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="69a72-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="69a72-108">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="69a72-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="69a72-109">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="69a72-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a72-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69a72-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="69a72-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="69a72-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69a72-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69a72-112">Attributes and Elements</span></span>  
 <span data-ttu-id="69a72-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69a72-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69a72-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="69a72-114">Attributes</span></span>  
  
|<span data-ttu-id="69a72-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="69a72-115">Attribute</span></span>|<span data-ttu-id="69a72-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="69a72-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69a72-117">type</span><span class="sxs-lookup"><span data-stu-id="69a72-117">type</span></span>|<span data-ttu-id="69a72-118">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="69a72-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69a72-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69a72-119">Child Elements</span></span>  
  
|<span data-ttu-id="69a72-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="69a72-120">Element</span></span>|<span data-ttu-id="69a72-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="69a72-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69a72-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="69a72-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="69a72-123">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="69a72-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69a72-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69a72-124">Parent Elements</span></span>  
  
|<span data-ttu-id="69a72-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="69a72-125">Element</span></span>|<span data-ttu-id="69a72-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="69a72-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69a72-127">\<add></span><span class="sxs-lookup"><span data-stu-id="69a72-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="69a72-128">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="69a72-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69a72-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69a72-129">Remarks</span></span>  
 <span data-ttu-id="69a72-130">Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="69a72-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="69a72-131">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="69a72-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a72-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69a72-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69a72-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="69a72-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="69a72-134">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="69a72-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="69a72-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="69a72-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="69a72-136">\<add></span><span class="sxs-lookup"><span data-stu-id="69a72-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
