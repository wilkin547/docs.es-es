---
title: Entity Data Model
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69b72a824e6f9468c9b3d86073243d506382e766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model"></a><span data-ttu-id="144db-102">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="144db-102">Entity Data Model</span></span>
<span data-ttu-id="144db-103">Entity Data Model (EDM) es un conjunto de conceptos que describen la estructura de los datos, independientemente del formato en el que estén almacenados.</span><span class="sxs-lookup"><span data-stu-id="144db-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="144db-104">EDM se basa en el modelo entidad-relación (Entity-Relationship Model) descrito por Peter Chen en 1976, pero también incorpora nuevas funciones y amplía sus usos tradicionales.</span><span class="sxs-lookup"><span data-stu-id="144db-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="144db-105">EDM soluciona los desafíos que plantea el tener datos almacenados en muchos formatos.</span><span class="sxs-lookup"><span data-stu-id="144db-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="144db-106">Considere, por ejemplo, un negocio que almacena los datos en bases de datos relacionales, archivos de texto, archivos XML, hojas de cálculo e informes.</span><span class="sxs-lookup"><span data-stu-id="144db-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="144db-107">Esto presenta importantes desafíos en el modelado de datos, el diseño de aplicaciones y el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="144db-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="144db-108">Al diseñar una aplicación orientada a datos, el desafío consiste en escribir un código eficaz y que se pueda mantener sin sacrificar la eficacia del acceso a los datos, el almacenamiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="144db-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="144db-109">Cuando los datos tienen una estructura relacional, el acceso a los datos, el almacenamiento y la escalabilidad resultan muy eficaces, pero es más difícil escribir un código eficaz y que se pueda mantener.</span><span class="sxs-lookup"><span data-stu-id="144db-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="144db-110">Cuando los datos tienen una estructura de objeto, se invierten las ventajas; es decir, la escritura de un código eficaz y que se pueda mantener se consigue a costa de la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="144db-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="144db-111">Aunque es posible encontrar el equilibrio adecuado entre ambos métodos, surgen nuevos desafíos cuando se mueven los datos de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="144db-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="144db-112">Entity Data Model resuelve estos desafíos describiendo la estructura de los datos en forma de entidades y relaciones que son independientes de cualquier esquema de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="144db-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="144db-113">Esto hace que el formato en el que están almacenados los datos sea irrelevante a la hora de diseñar y desarrollar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="144db-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="144db-114">Y, dado que las entidades y las relaciones describen la estructura de los datos tal como se usan en una aplicación (no el formato en el que están almacenados), pueden evolucionar al mismo tiempo que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="144db-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="144db-115">Un modelo conceptual (`conceptual model`) es una representación específica de la estructura de los datos en forma de entidades y relaciones, y normalmente se define mediante un lenguaje específico de dominio (DSL) que implementa los conceptos de EDM.</span><span class="sxs-lookup"><span data-stu-id="144db-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="144db-116">[Lenguaje de definición de esquemas conceptuales (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) es un ejemplo de este tipo de lenguaje específico de dominio.</span><span class="sxs-lookup"><span data-stu-id="144db-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="144db-117">Las entidades y relaciones descritas en un modelo conceptual se pueden considerar como abstracciones de objetos y asociaciones en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="144db-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="144db-118">Esto permite a los desarrolladores centrarse en el modelo conceptual sin tener que preocuparse por el esquema de almacenamiento, así como escribir el código teniendo en cuenta la eficacia y el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="144db-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="144db-119">Mientras tanto, los diseñadores del esquema de almacenamiento pueden centrarse en la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="144db-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="144db-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="144db-120">In This Section</span></span>  
 <span data-ttu-id="144db-121">Los temas de esta sección describen los conceptos de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="144db-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="144db-122">Cualquier ADSL que implemente EDM debe incluir los conceptos descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="144db-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="144db-123">Tenga en cuenta que la [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa CSDL para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="144db-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="144db-124">Para obtener más información, consulte [especificación de CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="144db-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="144db-125">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="144db-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="144db-126">Entity Data Model: espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="144db-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="144db-127">Entity Data Model: Tipos de datos primitivos</span><span class="sxs-lookup"><span data-stu-id="144db-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="144db-128">Entity Data Model: herencia</span><span class="sxs-lookup"><span data-stu-id="144db-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="144db-129">extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="144db-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="144db-130">multiplicidad de extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="144db-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="144db-131">conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="144db-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="144db-132">final del conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="144db-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="144db-133">tipo de asociación</span><span class="sxs-lookup"><span data-stu-id="144db-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="144db-134">tipo complejo</span><span class="sxs-lookup"><span data-stu-id="144db-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="144db-135">contenedor de entidades</span><span class="sxs-lookup"><span data-stu-id="144db-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="144db-136">clave de entidad</span><span class="sxs-lookup"><span data-stu-id="144db-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="144db-137">conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="144db-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="144db-138">tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="144db-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="144db-139">facet</span><span class="sxs-lookup"><span data-stu-id="144db-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="144db-140">propiedad de clave externa</span><span class="sxs-lookup"><span data-stu-id="144db-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="144db-141">función declarada por modelo</span><span class="sxs-lookup"><span data-stu-id="144db-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="144db-142">función definida por el modelo</span><span class="sxs-lookup"><span data-stu-id="144db-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="144db-143">propiedad de navegación</span><span class="sxs-lookup"><span data-stu-id="144db-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="144db-144">propiedad</span><span class="sxs-lookup"><span data-stu-id="144db-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="144db-145">restricción de integridad referencial</span><span class="sxs-lookup"><span data-stu-id="144db-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="144db-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="144db-146">See Also</span></span>  
 [<span data-ttu-id="144db-147">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="144db-147">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="144db-148">información general de archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="144db-148">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="144db-149">Especificación de CSDL</span><span class="sxs-lookup"><span data-stu-id="144db-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
