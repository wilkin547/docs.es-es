---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: b2445f12f1eaac03b3f3ab66f3d13a5f465a1133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753331"
---
# <a name="ltknowntypegt"></a><span data-ttu-id="6c566-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="6c566-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="6c566-103">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="6c566-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="6c566-104">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="6c566-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="6c566-105">Para obtener más información, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="6c566-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="6c566-106">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="6c566-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="6c566-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6c566-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="6c566-108">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="6c566-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="6c566-109">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="6c566-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="6c566-110">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="6c566-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c566-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c566-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="6c566-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c566-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c566-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c566-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6c566-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6c566-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c566-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c566-115">Attributes</span></span>  
  
|<span data-ttu-id="6c566-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="6c566-116">Attribute</span></span>|<span data-ttu-id="6c566-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c566-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c566-118">tipo</span><span class="sxs-lookup"><span data-stu-id="6c566-118">type</span></span>|<span data-ttu-id="6c566-119">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="6c566-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c566-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c566-120">Child Elements</span></span>  
  
|<span data-ttu-id="6c566-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c566-121">Element</span></span>|<span data-ttu-id="6c566-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c566-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c566-123">\<parámetro ></span><span class="sxs-lookup"><span data-stu-id="6c566-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="6c566-124">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6c566-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c566-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c566-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6c566-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c566-126">Element</span></span>|<span data-ttu-id="6c566-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c566-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c566-128">\<add></span><span class="sxs-lookup"><span data-stu-id="6c566-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="6c566-129">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="6c566-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c566-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c566-130">Remarks</span></span>  
 <span data-ttu-id="6c566-131">Para obtener más información sobre los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6c566-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6c566-132">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="6c566-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c566-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c566-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c566-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c566-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="6c566-135">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="6c566-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="6c566-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6c566-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="6c566-137">\<add></span><span class="sxs-lookup"><span data-stu-id="6c566-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
