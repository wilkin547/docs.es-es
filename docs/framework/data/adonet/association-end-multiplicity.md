---
description: 'Más información acerca de: multiplicidad de extremo de asociación'
title: multiplicidad de extremo de asociación
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 4b708406192e8a6e34119b47261d8986829f2a43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697704"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="4c82f-103">multiplicidad de extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="4c82f-103">association end multiplicity</span></span>

<span data-ttu-id="4c82f-104">La *multiplicidad de extremo de asociación* define el número de instancias de tipo de [entidad](entity-type.md) que pueden estar en un extremo de una [Asociación](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="4c82f-104">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="4c82f-105">Una multiplicidad de extremo de asociación puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c82f-105">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="4c82f-106">uno (1): indica que existe exactamente una instancia de tipo de entidad en el extremo de la asociación.</span><span class="sxs-lookup"><span data-stu-id="4c82f-106">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="4c82f-107">cero o uno (0..1): indica que pueden existir cero o una instancia de tipo de entidad en el extremo de la asociación.</span><span class="sxs-lookup"><span data-stu-id="4c82f-107">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="4c82f-108">Many ( \* ): indica que hay cero, una o más instancias de tipo de entidad en el extremo de la asociación.</span><span class="sxs-lookup"><span data-stu-id="4c82f-108">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="4c82f-109">Normalmente, una asociación se caracteriza por sus multiplicidades de extremo de asociación.</span><span class="sxs-lookup"><span data-stu-id="4c82f-109">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="4c82f-110">Por ejemplo, si los extremos de una asociación tienen multiplicidades uno (1) y varios ( \* ), la asociación se denomina una asociación uno a varios.</span><span class="sxs-lookup"><span data-stu-id="4c82f-110">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="4c82f-111">En el ejemplo siguiente, la asociación `PublishedBy` es una asociación uno a varios (un publicador publica muchos libros y un libro solo puede ser publicado por un publicador).</span><span class="sxs-lookup"><span data-stu-id="4c82f-111">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="4c82f-112">La asociación `WrittenBy` es una asociación varios a varios (un libro puede tener varios autores y un autor puede escribir varios libros).</span><span class="sxs-lookup"><span data-stu-id="4c82f-112">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c82f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c82f-113">Example</span></span>  

 <span data-ttu-id="4c82f-114">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="4c82f-114">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="4c82f-115">Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="4c82f-115">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="4c82f-116">La multiplicidad del `Publisher` extremo es uno (1) y la multiplicidad del `Book` extremo es muchos ( \* ).</span><span class="sxs-lookup"><span data-stu-id="4c82f-116">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="4c82f-118">El Entity Framework ADO.NET usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="4c82f-118">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="4c82f-119">El código CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior:</span><span class="sxs-lookup"><span data-stu-id="4c82f-119">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="4c82f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c82f-120">See also</span></span>

- [<span data-ttu-id="4c82f-121">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4c82f-121">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="4c82f-122">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4c82f-122">Entity Data Model</span></span>](entity-data-model.md)
