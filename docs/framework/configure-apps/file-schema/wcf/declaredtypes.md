---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: cef34a8836c7b17fe9a85cac190090f42653df14
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919263"
---
# <a name="declaredtypes"></a><span data-ttu-id="5fd6f-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="5fd6f-101">\<declaredTypes></span></span>
<span data-ttu-id="5fd6f-102">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="5fd6f-103">Para obtener más información sobre los contratos de datos y los tipos conocidos, consulte [Data Contract known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="5fd6f-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="5fd6f-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="5fd6f-104">system.runtime.serialization</span></span>  
<span data-ttu-id="5fd6f-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5fd6f-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="5fd6f-106">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="5fd6f-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fd6f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fd6f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fd6f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5fd6f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5fd6f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fd6f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5fd6f-110">Attributes</span></span>  
 <span data-ttu-id="5fd6f-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5fd6f-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5fd6f-112">Child Elements</span></span>  
  
|<span data-ttu-id="5fd6f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5fd6f-113">Element</span></span>|<span data-ttu-id="5fd6f-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5fd6f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fd6f-115">\<add></span><span class="sxs-lookup"><span data-stu-id="5fd6f-115">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="5fd6f-116">Agrega tipos que requieren tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5fd6f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5fd6f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5fd6f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5fd6f-118">Element</span></span>|<span data-ttu-id="5fd6f-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5fd6f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fd6f-120">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5fd6f-120">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="5fd6f-121">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fd6f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fd6f-122">Remarks</span></span>  
 <span data-ttu-id="5fd6f-123">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-123">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fd6f-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fd6f-124">Example</span></span>  
 <span data-ttu-id="5fd6f-125">En el código XML siguiente se muestran los tipos declarados y `DataContractSerializer` los tipos conocidos agregados a un elemento.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="5fd6f-126">El ejemplo muestra tres tipos que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-126">The example shows three types being added.</span></span> <span data-ttu-id="5fd6f-127">El primero es un tipo personalizado denominado "Orders" que usa un tipo conocido denominado "Item".</span><span class="sxs-lookup"><span data-stu-id="5fd6f-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="5fd6f-128">El segundo el tipo declarado es <xref:System.Collections.Generic.List%601> que usa `Item` como un tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="5fd6f-129">Finalmente, el tercer tipo declarado es <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="5fd6f-130">El tipo de clase <xref:System.Collections.Generic.Dictionary%602> es un tipo genérico, con dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="5fd6f-131">El primero representa la clave y el segundo representa el valor.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="5fd6f-132">El ejemplo siguiente agrega <xref:System.Collections.Generic.List%601> del segundo tipo (el valor) a la lista de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="5fd6f-133">Debe usar el atributo `index` para especificar qué parámetro de tipo se va a usar en el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="5fd6f-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="5fd6f-134">En este caso, el atributo de índice indica el tipo de valor establecido en "1" (la colección está basada en cero).</span><span class="sxs-lookup"><span data-stu-id="5fd6f-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fd6f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fd6f-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="5fd6f-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5fd6f-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="5fd6f-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="5fd6f-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="5fd6f-138">\<add></span><span class="sxs-lookup"><span data-stu-id="5fd6f-138">\<add></span></span>](add-of-declaredtypes-element.md)
