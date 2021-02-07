---
description: 'Más información acerca de: <knownType>'
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 205f799c81263be3dd08aae9efefb975b06a0cc7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725511"
---
# \<knownType>

<span data-ttu-id="d17ac-102">Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="d17ac-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="d17ac-103">El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado."</span><span class="sxs-lookup"><span data-stu-id="d17ac-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="d17ac-104">Para obtener más información, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="d17ac-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="d17ac-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d17ac-105">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="d17ac-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="d17ac-106">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d17ac-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d17ac-107">Attributes and Elements</span></span>  

 <span data-ttu-id="d17ac-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d17ac-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d17ac-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d17ac-109">Attributes</span></span>  
  
|<span data-ttu-id="d17ac-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="d17ac-110">Attribute</span></span>|<span data-ttu-id="d17ac-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d17ac-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d17ac-112">type</span><span class="sxs-lookup"><span data-stu-id="d17ac-112">type</span></span>|<span data-ttu-id="d17ac-113">Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="d17ac-113">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d17ac-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d17ac-114">Child Elements</span></span>  
  
|<span data-ttu-id="d17ac-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d17ac-115">Element</span></span>|<span data-ttu-id="d17ac-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d17ac-116">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="d17ac-117">Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="d17ac-117">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d17ac-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d17ac-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d17ac-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d17ac-119">Element</span></span>|<span data-ttu-id="d17ac-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d17ac-120">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="d17ac-121">Agrega un tipo declarado a la colección de tipos declarados.</span><span class="sxs-lookup"><span data-stu-id="d17ac-121">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d17ac-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d17ac-122">Remarks</span></span>  

 <span data-ttu-id="d17ac-123">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="d17ac-123">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d17ac-124">Vea [\<dataContractSerializer>](datacontractserializer-element.md) para obtener un ejemplo de uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="d17ac-124">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d17ac-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d17ac-125">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d17ac-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d17ac-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="d17ac-127">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="d17ac-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
