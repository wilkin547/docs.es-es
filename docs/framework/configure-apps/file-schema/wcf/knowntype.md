---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397871"
---
# <a name="knowntype"></a><span data-ttu-id="83c7c-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="83c7c-101">\<knownType></span></span>
<span data-ttu-id="83c7c-102">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="83c7c-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="83c7c-103">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="83c7c-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="83c7c-104">Para obtener más información, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="83c7c-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="83c7c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="83c7c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="83c7c-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="83c7c-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="83c7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="83c7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="83c7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="83c7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="83c7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="83c7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="83c7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> knownType**</span><span class="sxs-lookup"><span data-stu-id="83c7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c7c-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83c7c-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="83c7c-112">Type</span><span class="sxs-lookup"><span data-stu-id="83c7c-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83c7c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83c7c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="83c7c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83c7c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83c7c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="83c7c-115">Attributes</span></span>  
  
|<span data-ttu-id="83c7c-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="83c7c-116">Attribute</span></span>|<span data-ttu-id="83c7c-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83c7c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83c7c-118">type</span><span class="sxs-lookup"><span data-stu-id="83c7c-118">type</span></span>|<span data-ttu-id="83c7c-119">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="83c7c-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83c7c-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83c7c-120">Child Elements</span></span>  
  
|<span data-ttu-id="83c7c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="83c7c-121">Element</span></span>|<span data-ttu-id="83c7c-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83c7c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83c7c-123">\<> de parámetros</span><span class="sxs-lookup"><span data-stu-id="83c7c-123">\<parameter></span></span>](parameter.md)|<span data-ttu-id="83c7c-124">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="83c7c-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83c7c-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83c7c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="83c7c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="83c7c-126">Element</span></span>|<span data-ttu-id="83c7c-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83c7c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83c7c-128">\<add></span><span class="sxs-lookup"><span data-stu-id="83c7c-128">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="83c7c-129">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="83c7c-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83c7c-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83c7c-130">Remarks</span></span>  
 <span data-ttu-id="83c7c-131">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="83c7c-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="83c7c-132">Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="83c7c-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c7c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83c7c-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83c7c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c7c-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="83c7c-135">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="83c7c-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="83c7c-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="83c7c-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="83c7c-137">\<add></span><span class="sxs-lookup"><span data-stu-id="83c7c-137">\<add></span></span>](add-of-declaredtypes-element.md)
