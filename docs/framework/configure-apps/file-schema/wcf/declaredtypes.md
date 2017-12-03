---
title: '&lt;declaredTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80a2959395cf8f10ae8c5bc2ccd47ea97ffdaa30
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltdeclaredtypesgt"></a><span data-ttu-id="63a2c-102">&lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="63a2c-102">&lt;declaredTypes&gt;</span></span>
<span data-ttu-id="63a2c-103">Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.</span><span class="sxs-lookup"><span data-stu-id="63a2c-103">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="63a2c-104">Para obtener más información acerca de los contratos de datos y los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="63a2c-104">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="63a2c-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="63a2c-105">system.runtime.serialization</span></span>  
<span data-ttu-id="63a2c-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="63a2c-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="63a2c-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="63a2c-107">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a2c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63a2c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63a2c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63a2c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="63a2c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63a2c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63a2c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="63a2c-111">Attributes</span></span>  
 <span data-ttu-id="63a2c-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="63a2c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="63a2c-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63a2c-113">Child Elements</span></span>  
  
|<span data-ttu-id="63a2c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="63a2c-114">Element</span></span>|<span data-ttu-id="63a2c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="63a2c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63a2c-116">\<add></span><span class="sxs-lookup"><span data-stu-id="63a2c-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="63a2c-117">Agrega tipos que requieren tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="63a2c-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63a2c-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63a2c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="63a2c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="63a2c-119">Element</span></span>|<span data-ttu-id="63a2c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="63a2c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63a2c-121">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="63a2c-121">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="63a2c-122">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="63a2c-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63a2c-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63a2c-123">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="63a2c-124">los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="63a2c-124"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63a2c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63a2c-125">Example</span></span>  
 <span data-ttu-id="63a2c-126">El siguiente código XML muestra tipos declarados y tipos conocidos agregados a un `DataContractSerializer` elemento.</span><span class="sxs-lookup"><span data-stu-id="63a2c-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="63a2c-127">El ejemplo muestra tres tipos que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="63a2c-127">The example shows three types being added.</span></span> <span data-ttu-id="63a2c-128">El primero es un tipo personalizado denominado "Orders" que usa un tipo conocido denominado "Item".</span><span class="sxs-lookup"><span data-stu-id="63a2c-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="63a2c-129">El segundo el tipo declarado es <xref:System.Collections.Generic.List%601> que usa `Item` como un tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="63a2c-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="63a2c-130">Finalmente, el tercer tipo declarado es <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="63a2c-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="63a2c-131">El tipo de clase <xref:System.Collections.Generic.Dictionary%602> es un tipo genérico, con dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="63a2c-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="63a2c-132">El primero representa la clave y el segundo representa el valor.</span><span class="sxs-lookup"><span data-stu-id="63a2c-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="63a2c-133">El ejemplo siguiente agrega <xref:System.Collections.Generic.List%601> del segundo tipo (el valor) a la lista de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="63a2c-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="63a2c-134">Debe usar el atributo `index` para especificar qué parámetro de tipo se va a usar en el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="63a2c-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="63a2c-135">En este caso, el atributo de índice indica el tipo de valor establecido en "1" (la colección está basada en cero).</span><span class="sxs-lookup"><span data-stu-id="63a2c-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63a2c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="63a2c-136">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="63a2c-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="63a2c-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="63a2c-138">Los tipos conocidos de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="63a2c-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="63a2c-139">\<add></span><span class="sxs-lookup"><span data-stu-id="63a2c-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
