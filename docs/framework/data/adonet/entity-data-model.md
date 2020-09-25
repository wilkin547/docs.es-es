---
title: Entity Data Model
description: En el Entity Data Model se describe la estructura de los datos, independientemente de su forma almacenada, que aborda los desafíos resultantes del almacenamiento de datos en muchas formas.
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: 9323f652d1cfa27d442d45bd01e546f3b81d7e80
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200776"
---
# <a name="entity-data-model"></a><span data-ttu-id="2fa12-103">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="2fa12-103">Entity Data Model</span></span>

<span data-ttu-id="2fa12-104">Entity Data Model (EDM) es un conjunto de conceptos que describen la estructura de los datos, independientemente del formato en el que estén almacenados.</span><span class="sxs-lookup"><span data-stu-id="2fa12-104">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="2fa12-105">EDM se basa en el modelo entidad-relación (Entity-Relationship Model) descrito por Peter Chen en 1976, pero también incorpora nuevas funciones y amplía sus usos tradicionales.</span><span class="sxs-lookup"><span data-stu-id="2fa12-105">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="2fa12-106">EDM soluciona los desafíos que plantea el tener datos almacenados en muchos formatos.</span><span class="sxs-lookup"><span data-stu-id="2fa12-106">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="2fa12-107">Considere, por ejemplo, un negocio que almacena los datos en bases de datos relacionales, archivos de texto, archivos XML, hojas de cálculo e informes.</span><span class="sxs-lookup"><span data-stu-id="2fa12-107">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="2fa12-108">Esto presenta importantes desafíos en el modelado de datos, el diseño de aplicaciones y el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="2fa12-108">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="2fa12-109">Al diseñar una aplicación orientada a datos, el desafío consiste en escribir un código eficaz y que se pueda mantener sin sacrificar la eficacia del acceso a los datos, el almacenamiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="2fa12-109">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="2fa12-110">Cuando los datos tienen una estructura relacional, el acceso a los datos, el almacenamiento y la escalabilidad resultan muy eficaces, pero es más difícil escribir un código eficaz y que se pueda mantener.</span><span class="sxs-lookup"><span data-stu-id="2fa12-110">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="2fa12-111">Cuando los datos tienen una estructura de objeto, se invierten las ventajas; es decir, la escritura de un código eficaz y que se pueda mantener se consigue a costa de la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="2fa12-111">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="2fa12-112">Aunque es posible encontrar el equilibrio adecuado entre ambos métodos, surgen nuevos desafíos cuando se mueven los datos de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="2fa12-112">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="2fa12-113">Entity Data Model resuelve estos desafíos describiendo la estructura de los datos en forma de entidades y relaciones que son independientes de cualquier esquema de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="2fa12-113">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="2fa12-114">Esto hace que el formato en el que están almacenados los datos sea irrelevante a la hora de diseñar y desarrollar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2fa12-114">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="2fa12-115">Y, dado que las entidades y las relaciones describen la estructura de los datos tal como se usan en una aplicación (no el formato en el que están almacenados), pueden evolucionar al mismo tiempo que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2fa12-115">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="2fa12-116">Un modelo conceptual (`conceptual model`) es una representación específica de la estructura de los datos en forma de entidades y relaciones, y normalmente se define mediante un lenguaje específico de dominio (DSL) que implementa los conceptos de EDM.</span><span class="sxs-lookup"><span data-stu-id="2fa12-116">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="2fa12-117">El [lenguaje de definición de esquemas conceptuales (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) es un ejemplo de este tipo de lenguaje específico de dominio.</span><span class="sxs-lookup"><span data-stu-id="2fa12-117">[Conceptual schema definition language (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) is an example of such a domain-specific language.</span></span> <span data-ttu-id="2fa12-118">Las entidades y relaciones descritas en un modelo conceptual se pueden considerar como abstracciones de objetos y asociaciones en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2fa12-118">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="2fa12-119">Esto permite a los desarrolladores centrarse en el modelo conceptual sin tener que preocuparse por el esquema de almacenamiento, así como escribir el código teniendo en cuenta la eficacia y el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2fa12-119">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="2fa12-120">Mientras tanto, los diseñadores del esquema de almacenamiento pueden centrarse en la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="2fa12-120">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2fa12-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2fa12-121">In This Section</span></span>  

 <span data-ttu-id="2fa12-122">Los temas de esta sección describen los conceptos de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="2fa12-122">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="2fa12-123">Cualquier ADSL que implemente EDM debe incluir los conceptos descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="2fa12-123">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="2fa12-124">Tenga en cuenta que el [Entity Framework ADO.net](./ef/index.md) utiliza CSDL para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="2fa12-124">Note that the [ADO.NET Entity Framework](./ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="2fa12-125">Para obtener más información, consulta [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span><span class="sxs-lookup"><span data-stu-id="2fa12-125">For more information, see [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span>  
  
 [<span data-ttu-id="2fa12-126">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="2fa12-126">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="2fa12-127">Entity Data Model: Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="2fa12-127">Entity Data Model: Namespaces</span></span>](entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="2fa12-128">Entity Data Model: tipos de datos primitivos</span><span class="sxs-lookup"><span data-stu-id="2fa12-128">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="2fa12-129">Entity Data Model: Herencia</span><span class="sxs-lookup"><span data-stu-id="2fa12-129">Entity Data Model: Inheritance</span></span>](entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="2fa12-130">extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="2fa12-130">association end</span></span>](association-end.md)  
  
 [<span data-ttu-id="2fa12-131">multiplicidad de extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="2fa12-131">association end multiplicity</span></span>](association-end-multiplicity.md)  
  
 [<span data-ttu-id="2fa12-132">conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="2fa12-132">association set</span></span>](association-set.md)  
  
 [<span data-ttu-id="2fa12-133">extremo del conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="2fa12-133">association set end</span></span>](association-set-end.md)  
  
 [<span data-ttu-id="2fa12-134">tipo de asociación</span><span class="sxs-lookup"><span data-stu-id="2fa12-134">association type</span></span>](association-type.md)  
  
 [<span data-ttu-id="2fa12-135">tipo complejo</span><span class="sxs-lookup"><span data-stu-id="2fa12-135">complex type</span></span>](complex-type.md)  
  
 [<span data-ttu-id="2fa12-136">contenedor de entidades</span><span class="sxs-lookup"><span data-stu-id="2fa12-136">entity container</span></span>](entity-container.md)  
  
 [<span data-ttu-id="2fa12-137">clave de entidad</span><span class="sxs-lookup"><span data-stu-id="2fa12-137">entity key</span></span>](entity-key.md)  
  
 [<span data-ttu-id="2fa12-138">conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="2fa12-138">entity set</span></span>](entity-set.md)  
  
 [<span data-ttu-id="2fa12-139">tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="2fa12-139">entity type</span></span>](entity-type.md)  
  
 [<span data-ttu-id="2fa12-140">agrupa</span><span class="sxs-lookup"><span data-stu-id="2fa12-140">facet</span></span>](facet.md)  
  
 [<span data-ttu-id="2fa12-141">propiedad de clave externa</span><span class="sxs-lookup"><span data-stu-id="2fa12-141">foreign key property</span></span>](foreign-key-property.md)  
  
 [<span data-ttu-id="2fa12-142">función declarada por el modelo</span><span class="sxs-lookup"><span data-stu-id="2fa12-142">model-declared function</span></span>](model-declared-function.md)  
  
 [<span data-ttu-id="2fa12-143">función definida por el modelo</span><span class="sxs-lookup"><span data-stu-id="2fa12-143">model-defined function</span></span>](model-defined-function.md)  
  
 [<span data-ttu-id="2fa12-144">propiedad de navegación</span><span class="sxs-lookup"><span data-stu-id="2fa12-144">navigation property</span></span>](navigation-property.md)  
  
 [<span data-ttu-id="2fa12-145">property</span><span class="sxs-lookup"><span data-stu-id="2fa12-145">property</span></span>](property.md)  
  
 [<span data-ttu-id="2fa12-146">restricción de integridad referencial</span><span class="sxs-lookup"><span data-stu-id="2fa12-146">referential integrity constraint</span></span>](referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="2fa12-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fa12-147">See also</span></span>

- <span data-ttu-id="2fa12-148">[ADO.NET Entity Data Model herramientas](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2fa12-148">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="2fa12-149">[.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2fa12-149">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="2fa12-150">Especificación CSDL</span><span class="sxs-lookup"><span data-stu-id="2fa12-150">CSDL Specification</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
