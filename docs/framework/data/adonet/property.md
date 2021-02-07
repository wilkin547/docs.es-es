---
description: 'Más información acerca de: propiedad'
title: propiedad
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 8b25c19b0673817945fa6cc786589346462f7e61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754331"
---
# <a name="property"></a><span data-ttu-id="43efc-103">propiedad</span><span class="sxs-lookup"><span data-stu-id="43efc-103">property</span></span>

<span data-ttu-id="43efc-104">*Las propiedades* son los bloques de creación fundamentales de [tipos de entidad](entity-type.md) y [tipos complejos](complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="43efc-104">*Properties* are the fundamental building blocks of [entity types](entity-type.md) and [complex types](complex-type.md).</span></span> <span data-ttu-id="43efc-105">Las propiedades definen la forma y características de datos que una instancia del tipo de entidad o la instancia del tipo complejo contendrá.</span><span class="sxs-lookup"><span data-stu-id="43efc-105">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="43efc-106">Las propiedades en un modelo conceptual son análogas a las propiedades definidas en una clase.</span><span class="sxs-lookup"><span data-stu-id="43efc-106">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="43efc-107">Del mismo modo que las propiedades en una clase definen la forma de la clase y proporcionan información sobre los objetos, las propiedades en un modelo conceptual definen la forma de un tipo de entidad y proporcionan información sobre las instancias del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="43efc-107">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43efc-108">Las propiedades, tal y como se describen en este tema, son diferentes de las propiedades de navegación.</span><span class="sxs-lookup"><span data-stu-id="43efc-108">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="43efc-109">Para obtener más información, vea [propiedades de navegación](navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="43efc-109">For more information, see [navigation properties](navigation-property.md).</span></span>  
  
 <span data-ttu-id="43efc-110">Una definición de propiedad contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="43efc-110">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="43efc-111">nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="43efc-111">A property name.</span></span> <span data-ttu-id="43efc-112">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="43efc-112">(Required)</span></span>  
  
- <span data-ttu-id="43efc-113">Un tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="43efc-113">A property type.</span></span> <span data-ttu-id="43efc-114">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="43efc-114">(Required)</span></span>  
  
- <span data-ttu-id="43efc-115">Un conjunto de [aspectos](facet.md).</span><span class="sxs-lookup"><span data-stu-id="43efc-115">A set of [facets](facet.md).</span></span> <span data-ttu-id="43efc-116">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="43efc-116">(Optional)</span></span>  
  
 <span data-ttu-id="43efc-117">Una propiedad puede contener datos primitivos (como una cadena, un entero o un valor booleano) o estructura los datos (como un tipo complejo).</span><span class="sxs-lookup"><span data-stu-id="43efc-117">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="43efc-118">Las propiedades de tipo primitivo también se denominan propiedades escalares.</span><span class="sxs-lookup"><span data-stu-id="43efc-118">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="43efc-119">Para obtener más información, vea [Entity Data Model: tipos de datos primitivos](entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="43efc-119">For more information, see [Entity Data Model: Primitive Data Types](entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43efc-120">Un tipo complejo puede, por sí mismo, tener propiedades complejas.</span><span class="sxs-lookup"><span data-stu-id="43efc-120">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43efc-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43efc-121">Example</span></span>  

 <span data-ttu-id="43efc-122">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="43efc-122">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="43efc-123">Cada tipo de entidad tiene varias propiedades, aunque la información de tipo para cada propiedad no se muestra en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="43efc-123">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="43efc-124">Las propiedades que son [claves de entidad](entity-key.md) se denotan con (Key).</span><span class="sxs-lookup"><span data-stu-id="43efc-124">Properties that are [entity keys](entity-key.md) are denoted with (Key).</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="43efc-126">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="43efc-126">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="43efc-127">En el siguiente CSDL se define el tipo de entidad `Book` (como se muestra en el diagrama anterior) y se indica el tipo y nombre de cada propiedad utilizando atributos XML.</span><span class="sxs-lookup"><span data-stu-id="43efc-127">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="43efc-128">Una faceta opcional, `Nullable`, también se define utilizando un atributo de XML.</span><span class="sxs-lookup"><span data-stu-id="43efc-128">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="43efc-129">Es posible que una de las propiedades mostradas en el diagrama sea una propiedad de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="43efc-129">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="43efc-130">Por ejemplo, la propiedad `Address` en el tipo de entidad `Publisher` podría ser una propiedad de tipo complejo compuesta de varias propiedades escalares, como `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="43efc-130">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="43efc-131">La representación CSDL de un tipo complejo como el anterior sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="43efc-131">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="43efc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="43efc-132">See also</span></span>

- [<span data-ttu-id="43efc-133">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="43efc-133">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="43efc-134">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="43efc-134">Entity Data Model</span></span>](entity-data-model.md)
