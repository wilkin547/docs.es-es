---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928868"
---
# <a name="knowntype"></a><span data-ttu-id="82a96-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="82a96-101">\<knownType></span></span>
<span data-ttu-id="82a96-102">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="82a96-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="82a96-103">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="82a96-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="82a96-104">Para obtener más información, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="82a96-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="82a96-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="82a96-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="82a96-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="82a96-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="82a96-107">\<declaredTypes >, elemento</span><span class="sxs-lookup"><span data-stu-id="82a96-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="82a96-108">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="82a96-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="82a96-109">\<knownType >, elemento</span><span class="sxs-lookup"><span data-stu-id="82a96-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a96-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82a96-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="82a96-111">Type</span><span class="sxs-lookup"><span data-stu-id="82a96-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82a96-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="82a96-112">Attributes and Elements</span></span>  
 <span data-ttu-id="82a96-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="82a96-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82a96-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="82a96-114">Attributes</span></span>  
  
|<span data-ttu-id="82a96-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="82a96-115">Attribute</span></span>|<span data-ttu-id="82a96-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="82a96-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82a96-117">type</span><span class="sxs-lookup"><span data-stu-id="82a96-117">type</span></span>|<span data-ttu-id="82a96-118">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="82a96-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82a96-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="82a96-119">Child Elements</span></span>  
  
|<span data-ttu-id="82a96-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="82a96-120">Element</span></span>|<span data-ttu-id="82a96-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="82a96-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82a96-122">\<> de parámetros</span><span class="sxs-lookup"><span data-stu-id="82a96-122">\<parameter></span></span>](parameter.md)|<span data-ttu-id="82a96-123">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="82a96-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82a96-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="82a96-124">Parent Elements</span></span>  
  
|<span data-ttu-id="82a96-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="82a96-125">Element</span></span>|<span data-ttu-id="82a96-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="82a96-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82a96-127">\<add></span><span class="sxs-lookup"><span data-stu-id="82a96-127">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="82a96-128">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="82a96-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a96-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82a96-129">Remarks</span></span>  
 <span data-ttu-id="82a96-130">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="82a96-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="82a96-131">Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="82a96-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82a96-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82a96-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82a96-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a96-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="82a96-134">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="82a96-134">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="82a96-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="82a96-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="82a96-136">\<add></span><span class="sxs-lookup"><span data-stu-id="82a96-136">\<add></span></span>](add-of-declaredtypes-element.md)
