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
ms.openlocfilehash: d347afb183b23410359a0972d7fd3b1f851971bd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265002"
---
# <a name="declaredtypes"></a><span data-ttu-id="22ded-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="22ded-101">\<declaredTypes></span></span>
<span data-ttu-id="22ded-102">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="22ded-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="22ded-103">Para obtener más información acerca de los contratos de datos y los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="22ded-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="22ded-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="22ded-104">system.runtime.serialization</span></span>  
<span data-ttu-id="22ded-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="22ded-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="22ded-106">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="22ded-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ded-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22ded-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22ded-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22ded-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22ded-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22ded-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22ded-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="22ded-110">Attributes</span></span>  
 <span data-ttu-id="22ded-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22ded-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22ded-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22ded-112">Child Elements</span></span>  
  
|<span data-ttu-id="22ded-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="22ded-113">Element</span></span>|<span data-ttu-id="22ded-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="22ded-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22ded-115">\<add></span><span class="sxs-lookup"><span data-stu-id="22ded-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="22ded-116">Agrega tipos que requieren tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="22ded-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22ded-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22ded-117">Parent Elements</span></span>  
  
|<span data-ttu-id="22ded-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="22ded-118">Element</span></span>|<span data-ttu-id="22ded-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="22ded-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22ded-120">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="22ded-120">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="22ded-121">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="22ded-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ded-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22ded-122">Remarks</span></span>  
 <span data-ttu-id="22ded-123">Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="22ded-123">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22ded-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22ded-124">Example</span></span>  
 <span data-ttu-id="22ded-125">El siguiente código XML muestra tipos declarados y tipos conocidos agregados a un `DataContractSerializer` elemento.</span><span class="sxs-lookup"><span data-stu-id="22ded-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="22ded-126">El ejemplo muestra tres tipos que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="22ded-126">The example shows three types being added.</span></span> <span data-ttu-id="22ded-127">El primero es un tipo personalizado denominado "Orders" que usa un tipo conocido denominado "Item".</span><span class="sxs-lookup"><span data-stu-id="22ded-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="22ded-128">El segundo el tipo declarado es <xref:System.Collections.Generic.List%601> que usa `Item` como un tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="22ded-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="22ded-129">Finalmente, el tercer tipo declarado es <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="22ded-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="22ded-130">El tipo de clase <xref:System.Collections.Generic.Dictionary%602> es un tipo genérico, con dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="22ded-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="22ded-131">El primero representa la clave y el segundo representa el valor.</span><span class="sxs-lookup"><span data-stu-id="22ded-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="22ded-132">El ejemplo siguiente agrega <xref:System.Collections.Generic.List%601> del segundo tipo (el valor) a la lista de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="22ded-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="22ded-133">Debe usar el atributo `index` para especificar qué parámetro de tipo se va a usar en el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="22ded-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="22ded-134">En este caso, el atributo de índice indica el tipo de valor establecido en "1" (la colección está basada en cero).</span><span class="sxs-lookup"><span data-stu-id="22ded-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22ded-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="22ded-135">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="22ded-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="22ded-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="22ded-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="22ded-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="22ded-138">\<add></span><span class="sxs-lookup"><span data-stu-id="22ded-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
