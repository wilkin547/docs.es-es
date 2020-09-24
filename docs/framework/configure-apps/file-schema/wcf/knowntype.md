---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6bb6a419d863172951d82a67de044cb8cfc30f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183798"
---
# \<knownType>

<span data-ttu-id="62784-101">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="62784-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="62784-102">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="62784-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="62784-103">Para obtener más información, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="62784-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="62784-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62784-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="62784-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="62784-105">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62784-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="62784-106">Attributes and Elements</span></span>  

 <span data-ttu-id="62784-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="62784-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62784-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="62784-108">Attributes</span></span>  
  
|<span data-ttu-id="62784-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="62784-109">Attribute</span></span>|<span data-ttu-id="62784-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="62784-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62784-111">type</span><span class="sxs-lookup"><span data-stu-id="62784-111">type</span></span>|<span data-ttu-id="62784-112">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="62784-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62784-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="62784-113">Child Elements</span></span>  
  
|<span data-ttu-id="62784-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="62784-114">Element</span></span>|<span data-ttu-id="62784-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="62784-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="62784-116">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="62784-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62784-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62784-117">Parent Elements</span></span>  
  
|<span data-ttu-id="62784-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="62784-118">Element</span></span>|<span data-ttu-id="62784-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="62784-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="62784-120">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="62784-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62784-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62784-121">Remarks</span></span>  

 <span data-ttu-id="62784-122">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="62784-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="62784-123">Vea [\<dataContractSerializer>](datacontractserializer-element.md) para obtener un ejemplo de uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="62784-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62784-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62784-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62784-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62784-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="62784-126">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="62784-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
