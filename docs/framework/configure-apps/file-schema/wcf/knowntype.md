---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397871"
---
# \<knownType>
<span data-ttu-id="5d481-101">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="5d481-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="5d481-102">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="5d481-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="5d481-103">Para obtener más información, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="5d481-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="5d481-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d481-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="5d481-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d481-105">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d481-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d481-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5d481-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d481-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d481-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d481-108">Attributes</span></span>  
  
|<span data-ttu-id="5d481-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d481-109">Attribute</span></span>|<span data-ttu-id="5d481-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d481-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d481-111">type</span><span class="sxs-lookup"><span data-stu-id="5d481-111">type</span></span>|<span data-ttu-id="5d481-112">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="5d481-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d481-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d481-113">Child Elements</span></span>  
  
|<span data-ttu-id="5d481-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d481-114">Element</span></span>|<span data-ttu-id="5d481-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d481-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="5d481-116">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5d481-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d481-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d481-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5d481-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d481-118">Element</span></span>|<span data-ttu-id="5d481-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d481-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="5d481-120">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="5d481-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d481-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d481-121">Remarks</span></span>  
 <span data-ttu-id="5d481-122">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="5d481-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="5d481-123">Vea [\<dataContractSerializer>](datacontractserializer-element.md) para obtener un ejemplo de uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="5d481-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d481-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d481-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d481-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d481-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="5d481-126">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="5d481-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
