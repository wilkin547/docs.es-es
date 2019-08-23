---
title: <add>del <declaredTypes> elemento
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 1ea008dcc72d555b00e9648ace95bb9522ffc2c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920187"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="be929-102">\<Agregar > del \<elemento > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="be929-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="be929-103">Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="be929-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="be929-104">Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="be929-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="be929-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="be929-105">system.runtime.serialization</span></span>  
<span data-ttu-id="be929-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="be929-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="be929-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="be929-107">\<declaredTypes></span></span>  
<span data-ttu-id="be929-108">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="be929-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be929-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be929-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be929-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="be929-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be929-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="be929-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be929-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="be929-112">Attributes</span></span>  
  
|<span data-ttu-id="be929-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="be929-113">Attribute</span></span>|<span data-ttu-id="be929-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="be929-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be929-115">type</span><span class="sxs-lookup"><span data-stu-id="be929-115">type</span></span>|<span data-ttu-id="be929-116">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="be929-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="be929-117">Especifica el nombre del tipo (incluido el espacio de nombres), nombre de ensamblado, número de versión, referencia cultural y símbolo (token) de clave pública.</span><span class="sxs-lookup"><span data-stu-id="be929-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be929-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="be929-118">Child Elements</span></span>  
  
|<span data-ttu-id="be929-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="be929-119">Element</span></span>|<span data-ttu-id="be929-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="be929-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be929-121">\<knownType></span><span class="sxs-lookup"><span data-stu-id="be929-121">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="be929-122">Especifica el tipo conocido del tipo declarado que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="be929-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="be929-123">Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="be929-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be929-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="be929-124">Parent Elements</span></span>  
  
|<span data-ttu-id="be929-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="be929-125">Element</span></span>|<span data-ttu-id="be929-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="be929-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be929-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="be929-127">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="be929-128">Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="be929-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be929-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be929-129">Remarks</span></span>  
 <span data-ttu-id="be929-130">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="be929-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="be929-131">Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="be929-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be929-132">Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="be929-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="be929-133">Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.</span><span class="sxs-lookup"><span data-stu-id="be929-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be929-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be929-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be929-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="be929-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="be929-136">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="be929-136">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="be929-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="be929-137">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="be929-138">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="be929-138">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
