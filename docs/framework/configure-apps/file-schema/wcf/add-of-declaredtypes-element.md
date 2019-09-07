---
title: <add>del <declaredTypes> elemento
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400654"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="bc21f-102">\<Agregar > del \<elemento > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="bc21f-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="bc21f-103">Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="bc21f-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="bc21f-104">Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="bc21f-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="bc21f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bc21f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bc21f-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="bc21f-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="bc21f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="bc21f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="bc21f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="bc21f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="bc21f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="bc21f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc21f-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc21f-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc21f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bc21f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bc21f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bc21f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc21f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="bc21f-113">Attributes</span></span>  
  
|<span data-ttu-id="bc21f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="bc21f-114">Attribute</span></span>|<span data-ttu-id="bc21f-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc21f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc21f-116">type</span><span class="sxs-lookup"><span data-stu-id="bc21f-116">type</span></span>|<span data-ttu-id="bc21f-117">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="bc21f-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="bc21f-118">Especifica el nombre del tipo (incluido el espacio de nombres), nombre de ensamblado, número de versión, referencia cultural y símbolo (token) de clave pública.</span><span class="sxs-lookup"><span data-stu-id="bc21f-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc21f-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bc21f-119">Child Elements</span></span>  
  
|<span data-ttu-id="bc21f-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc21f-120">Element</span></span>|<span data-ttu-id="bc21f-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc21f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc21f-122">\<knownType></span><span class="sxs-lookup"><span data-stu-id="bc21f-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="bc21f-123">Especifica el tipo conocido del tipo declarado que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="bc21f-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="bc21f-124">Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="bc21f-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc21f-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bc21f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bc21f-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc21f-126">Element</span></span>|<span data-ttu-id="bc21f-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc21f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc21f-128">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="bc21f-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="bc21f-129">Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bc21f-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc21f-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc21f-130">Remarks</span></span>  
 <span data-ttu-id="bc21f-131">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="bc21f-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="bc21f-132">Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="bc21f-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc21f-133">Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="bc21f-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="bc21f-134">Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.</span><span class="sxs-lookup"><span data-stu-id="bc21f-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc21f-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc21f-135">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="bc21f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc21f-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="bc21f-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="bc21f-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="bc21f-138">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="bc21f-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="bc21f-139">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="bc21f-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
