---
title: <add> del <declaredTypes> elemento
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 9af47848b03074ec88f38a5884089bc50239ee50
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201673"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="2a081-102">\<add> del \<declaredTypes> elemento</span><span class="sxs-lookup"><span data-stu-id="2a081-102">\<add> of \<declaredTypes> Element</span></span>

<span data-ttu-id="2a081-103">Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="2a081-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="2a081-104">Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="2a081-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="2a081-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a081-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a081-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2a081-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2a081-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2a081-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a081-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a081-108">Attributes</span></span>  
  
|<span data-ttu-id="2a081-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="2a081-109">Attribute</span></span>|<span data-ttu-id="2a081-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a081-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a081-111">type</span><span class="sxs-lookup"><span data-stu-id="2a081-111">type</span></span>|<span data-ttu-id="2a081-112">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="2a081-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="2a081-113">Especifica el nombre del tipo (incluido el espacio de nombres), nombre de ensamblado, número de versión, referencia cultural y símbolo (token) de clave pública.</span><span class="sxs-lookup"><span data-stu-id="2a081-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a081-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2a081-114">Child Elements</span></span>  
  
|<span data-ttu-id="2a081-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a081-115">Element</span></span>|<span data-ttu-id="2a081-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a081-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="2a081-117">Especifica el tipo conocido del tipo declarado que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="2a081-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="2a081-118">Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="2a081-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a081-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2a081-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2a081-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a081-120">Element</span></span>|<span data-ttu-id="2a081-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a081-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="2a081-122">Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2a081-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a081-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a081-123">Remarks</span></span>  

 <span data-ttu-id="2a081-124">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="2a081-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="2a081-125">Vea [\<dataContractSerializer>](datacontractserializer-element.md) para obtener un ejemplo de uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="2a081-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a081-126">Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="2a081-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="2a081-127">Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.</span><span class="sxs-lookup"><span data-stu-id="2a081-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a081-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a081-128">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a081-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a081-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="2a081-130">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="2a081-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="2a081-131">\<add> de \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="2a081-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
