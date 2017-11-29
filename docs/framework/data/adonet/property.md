---
title: propiedad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c052c53488fde0ea767a46f51ef349dd6a7d2766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="property"></a><span data-ttu-id="a2390-102">propiedad</span><span class="sxs-lookup"><span data-stu-id="a2390-102">property</span></span>
<span data-ttu-id="a2390-103">*Propiedades* son los bloques de creación fundamentales de [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) y [tipos complejos](../../../../docs/framework/data/adonet/complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="a2390-103">*Properties* are the fundamental building blocks of [entity types](../../../../docs/framework/data/adonet/entity-type.md) and [complex types](../../../../docs/framework/data/adonet/complex-type.md).</span></span> <span data-ttu-id="a2390-104">Las propiedades definen la forma y características de datos que una instancia del tipo de entidad o la instancia del tipo complejo contendrá.</span><span class="sxs-lookup"><span data-stu-id="a2390-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="a2390-105">Las propiedades en un modelo conceptual son análogas a las propiedades definidas en una clase.</span><span class="sxs-lookup"><span data-stu-id="a2390-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="a2390-106">Del mismo modo que las propiedades en una clase definen la forma de la clase y proporcionan información sobre los objetos, las propiedades en un modelo conceptual definen la forma de un tipo de entidad y proporcionan información sobre las instancias del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="a2390-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2390-107">Las propiedades, tal y como se describen en este tema, son diferentes de las propiedades de navegación.</span><span class="sxs-lookup"><span data-stu-id="a2390-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="a2390-108">Para obtener más información, consulte [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="a2390-108">For more information, see [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md).</span></span>  
  
 <span data-ttu-id="a2390-109">Una definición de propiedad contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a2390-109">A property definition contains the following information:</span></span>  
  
-   <span data-ttu-id="a2390-110">nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a2390-110">A property name.</span></span> <span data-ttu-id="a2390-111">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="a2390-111">(Required)</span></span>  
  
-   <span data-ttu-id="a2390-112">Un tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a2390-112">A property type.</span></span> <span data-ttu-id="a2390-113">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="a2390-113">(Required)</span></span>  
  
-   <span data-ttu-id="a2390-114">Un conjunto de [facetas](../../../../docs/framework/data/adonet/facet.md).</span><span class="sxs-lookup"><span data-stu-id="a2390-114">A set of [facets](../../../../docs/framework/data/adonet/facet.md).</span></span> <span data-ttu-id="a2390-115">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="a2390-115">(Optional)</span></span>  
  
 <span data-ttu-id="a2390-116">Una propiedad puede contener datos primitivos (como una cadena, un entero o un valor booleano) o estructura los datos (como un tipo complejo).</span><span class="sxs-lookup"><span data-stu-id="a2390-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="a2390-117">Las propiedades de tipo primitivo también se denominan propiedades escalares.</span><span class="sxs-lookup"><span data-stu-id="a2390-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="a2390-118">Para obtener más información, consulte [Entity Data Model: tipos de datos primitivos](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a2390-118">For more information, see [Entity Data Model: Primitive Data Types](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2390-119">Un tipo complejo puede, por sí mismo, tener propiedades complejas.</span><span class="sxs-lookup"><span data-stu-id="a2390-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2390-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2390-120">Example</span></span>  
 <span data-ttu-id="a2390-121">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="a2390-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="a2390-122">Cada tipo de entidad tiene varias propiedades, aunque la información de tipo para cada propiedad no se muestra en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="a2390-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="a2390-123">Propiedades que son [claves de entidad](../../../../docs/framework/data/adonet/entity-key.md) se denotan con (Key).</span><span class="sxs-lookup"><span data-stu-id="a2390-123">Properties that are [entity keys](../../../../docs/framework/data/adonet/entity-key.md) are denoted with (Key).</span></span>  
  
 <span data-ttu-id="a2390-124">![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="a2390-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="a2390-125">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="a2390-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a2390-126">En el siguiente CSDL se define el tipo de entidad `Book` (como se muestra en el diagrama anterior) y se indica el tipo y nombre de cada propiedad utilizando atributos XML.</span><span class="sxs-lookup"><span data-stu-id="a2390-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="a2390-127">Una faceta opcional, `Nullable`, también se define utilizando un atributo de XML.</span><span class="sxs-lookup"><span data-stu-id="a2390-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="a2390-128">Es posible que una de las propiedades mostradas en el diagrama sea una propiedad de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="a2390-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="a2390-129">Por ejemplo, la propiedad `Address` en el tipo de entidad `Publisher` podría ser una propiedad de tipo complejo compuesta de varias propiedades escalares, como `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="a2390-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="a2390-130">La representación CSDL de un tipo complejo como el anterior sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="a2390-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a2390-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2390-131">See Also</span></span>  
 [<span data-ttu-id="a2390-132">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="a2390-132">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="a2390-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a2390-133">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
