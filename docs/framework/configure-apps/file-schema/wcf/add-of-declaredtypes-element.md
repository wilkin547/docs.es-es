---
title: '&lt;add&gt; de &lt;declaredTypes&gt; (elemento)'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 90eaf11ce8b9e3675a23ed3875680b03f149b56b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="b2d5f-102">&lt;add&gt; de &lt;declaredTypes&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="b2d5f-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="b2d5f-103">Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="b2d5f-104">Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="b2d5f-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="b2d5f-105">system.runtime.serialization</span></span>  
<span data-ttu-id="b2d5f-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="b2d5f-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-107">\<declaredTypes></span></span>  
<span data-ttu-id="b2d5f-108">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d5f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2d5f-109">Syntax</span></span>  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2d5f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b2d5f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2d5f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2d5f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b2d5f-112">Attributes</span></span>  
  
|<span data-ttu-id="b2d5f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b2d5f-113">Attribute</span></span>|<span data-ttu-id="b2d5f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d5f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2d5f-115">tipo</span><span class="sxs-lookup"><span data-stu-id="b2d5f-115">type</span></span>|<span data-ttu-id="b2d5f-116">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b2d5f-117">Especifica el nombre del tipo (incluido el espacio de nombres), nombre de ensamblado, número de versión, referencia cultural y símbolo (token) de clave pública.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2d5f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b2d5f-118">Child Elements</span></span>  
  
|<span data-ttu-id="b2d5f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2d5f-119">Element</span></span>|<span data-ttu-id="b2d5f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d5f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2d5f-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="b2d5f-122">Especifica el tipo conocido del tipo declarado que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="b2d5f-123">Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2d5f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b2d5f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b2d5f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2d5f-125">Element</span></span>|<span data-ttu-id="b2d5f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d5f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2d5f-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="b2d5f-128">Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2d5f-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2d5f-129">Remarks</span></span>  
 <span data-ttu-id="b2d5f-130">Para obtener más información sobre los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b2d5f-131">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2d5f-132">Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="b2d5f-133">Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2d5f-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2d5f-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2d5f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2d5f-135">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="b2d5f-136">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="b2d5f-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="b2d5f-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="b2d5f-138">\<Agregar > de \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b2d5f-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
