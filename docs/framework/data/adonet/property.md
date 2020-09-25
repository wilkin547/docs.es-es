---
title: propiedad
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 6aeb29c5aa608987466ec858416a4ac141ff1da3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180925"
---
# <a name="property"></a><span data-ttu-id="345ee-102">propiedad</span><span class="sxs-lookup"><span data-stu-id="345ee-102">property</span></span>

<span data-ttu-id="345ee-103">*Las propiedades* son los bloques de creación fundamentales de [tipos de entidad](entity-type.md) y [tipos complejos](complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="345ee-103">*Properties* are the fundamental building blocks of [entity types](entity-type.md) and [complex types](complex-type.md).</span></span> <span data-ttu-id="345ee-104">Las propiedades definen la forma y características de datos que una instancia del tipo de entidad o la instancia del tipo complejo contendrá.</span><span class="sxs-lookup"><span data-stu-id="345ee-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="345ee-105">Las propiedades en un modelo conceptual son análogas a las propiedades definidas en una clase.</span><span class="sxs-lookup"><span data-stu-id="345ee-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="345ee-106">Del mismo modo que las propiedades en una clase definen la forma de la clase y proporcionan información sobre los objetos, las propiedades en un modelo conceptual definen la forma de un tipo de entidad y proporcionan información sobre las instancias del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="345ee-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="345ee-107">Las propiedades, tal y como se describen en este tema, son diferentes de las propiedades de navegación.</span><span class="sxs-lookup"><span data-stu-id="345ee-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="345ee-108">Para obtener más información, vea [propiedades de navegación](navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="345ee-108">For more information, see [navigation properties](navigation-property.md).</span></span>  
  
 <span data-ttu-id="345ee-109">Una definición de propiedad contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="345ee-109">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="345ee-110">nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="345ee-110">A property name.</span></span> <span data-ttu-id="345ee-111">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="345ee-111">(Required)</span></span>  
  
- <span data-ttu-id="345ee-112">Un tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="345ee-112">A property type.</span></span> <span data-ttu-id="345ee-113">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="345ee-113">(Required)</span></span>  
  
- <span data-ttu-id="345ee-114">Un conjunto de [aspectos](facet.md).</span><span class="sxs-lookup"><span data-stu-id="345ee-114">A set of [facets](facet.md).</span></span> <span data-ttu-id="345ee-115">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="345ee-115">(Optional)</span></span>  
  
 <span data-ttu-id="345ee-116">Una propiedad puede contener datos primitivos (como una cadena, un entero o un valor booleano) o estructura los datos (como un tipo complejo).</span><span class="sxs-lookup"><span data-stu-id="345ee-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="345ee-117">Las propiedades de tipo primitivo también se denominan propiedades escalares.</span><span class="sxs-lookup"><span data-stu-id="345ee-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="345ee-118">Para obtener más información, vea [Entity Data Model: tipos de datos primitivos](entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="345ee-118">For more information, see [Entity Data Model: Primitive Data Types](entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="345ee-119">Un tipo complejo puede, por sí mismo, tener propiedades complejas.</span><span class="sxs-lookup"><span data-stu-id="345ee-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="345ee-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345ee-120">Example</span></span>  

 <span data-ttu-id="345ee-121">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="345ee-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="345ee-122">Cada tipo de entidad tiene varias propiedades, aunque la información de tipo para cada propiedad no se muestra en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="345ee-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="345ee-123">Las propiedades que son [claves de entidad](entity-key.md) se denotan con (Key).</span><span class="sxs-lookup"><span data-stu-id="345ee-123">Properties that are [entity keys](entity-key.md) are denoted with (Key).</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="345ee-125">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="345ee-125">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="345ee-126">En el siguiente CSDL se define el tipo de entidad `Book` (como se muestra en el diagrama anterior) y se indica el tipo y nombre de cada propiedad utilizando atributos XML.</span><span class="sxs-lookup"><span data-stu-id="345ee-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="345ee-127">Una faceta opcional, `Nullable`, también se define utilizando un atributo de XML.</span><span class="sxs-lookup"><span data-stu-id="345ee-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="345ee-128">Es posible que una de las propiedades mostradas en el diagrama sea una propiedad de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="345ee-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="345ee-129">Por ejemplo, la propiedad `Address` en el tipo de entidad `Publisher` podría ser una propiedad de tipo complejo compuesta de varias propiedades escalares, como `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="345ee-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="345ee-130">La representación CSDL de un tipo complejo como el anterior sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="345ee-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="345ee-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="345ee-131">See also</span></span>

- [<span data-ttu-id="345ee-132">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="345ee-132">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="345ee-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="345ee-133">Entity Data Model</span></span>](entity-data-model.md)
