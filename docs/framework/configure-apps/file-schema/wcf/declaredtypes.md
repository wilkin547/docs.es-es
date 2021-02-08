---
description: 'Más información acerca de: <declaredTypes>'
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: e5f60209dd556edc7cf47b01b1a58c1f17d74eac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803937"
---
# \<declaredTypes>

<span data-ttu-id="a6fef-102">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="a6fef-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="a6fef-103">Para obtener más información sobre los contratos de datos y los tipos conocidos, consulte [Data Contract known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="a6fef-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="a6fef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6fef-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6fef-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6fef-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a6fef-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6fef-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6fef-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6fef-107">Attributes</span></span>  

 <span data-ttu-id="a6fef-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a6fef-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6fef-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6fef-109">Child Elements</span></span>  
  
|<span data-ttu-id="a6fef-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6fef-110">Element</span></span>|<span data-ttu-id="a6fef-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6fef-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="a6fef-112">Agrega tipos que requieren tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="a6fef-112">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6fef-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6fef-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a6fef-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6fef-114">Element</span></span>|<span data-ttu-id="a6fef-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6fef-115">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="a6fef-116">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a6fef-116">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6fef-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a6fef-117">Remarks</span></span>  

 <span data-ttu-id="a6fef-118">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="a6fef-118">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6fef-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6fef-119">Example</span></span>  

 <span data-ttu-id="a6fef-120">En el código XML siguiente se muestran los tipos declarados y los tipos conocidos agregados a un `DataContractSerializer` elemento.</span><span class="sxs-lookup"><span data-stu-id="a6fef-120">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="a6fef-121">El ejemplo muestra tres tipos que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="a6fef-121">The example shows three types being added.</span></span> <span data-ttu-id="a6fef-122">El primero es un tipo personalizado denominado "Orders" que usa un tipo conocido denominado "Item".</span><span class="sxs-lookup"><span data-stu-id="a6fef-122">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="a6fef-123">El segundo el tipo declarado es <xref:System.Collections.Generic.List%601> que usa `Item` como un tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="a6fef-123">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="a6fef-124">Finalmente, el tercer tipo declarado es <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="a6fef-124">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="a6fef-125">El tipo de clase <xref:System.Collections.Generic.Dictionary%602> es un tipo genérico, con dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="a6fef-125">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="a6fef-126">El primero representa la clave y el segundo representa el valor.</span><span class="sxs-lookup"><span data-stu-id="a6fef-126">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="a6fef-127">El ejemplo siguiente agrega <xref:System.Collections.Generic.List%601> del segundo tipo (el valor) a la lista de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="a6fef-127">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="a6fef-128">Debe usar el atributo `index` para especificar qué parámetro de tipo se va a usar en el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="a6fef-128">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="a6fef-129">En este caso, el atributo de índice indica el tipo de valor establecido en "1" (la colección está basada en cero).</span><span class="sxs-lookup"><span data-stu-id="a6fef-129">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="a6fef-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6fef-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="a6fef-131">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="a6fef-131">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<add>](add-of-declaredtypes-element.md)
