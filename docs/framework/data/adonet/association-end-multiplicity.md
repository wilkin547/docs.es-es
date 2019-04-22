---
title: multiplicidad de extremo de asociación
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 59eed56204543adf405cfc7c71a49697a9e18374
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135036"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="b250b-102">multiplicidad de extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="b250b-102">association end multiplicity</span></span>
<span data-ttu-id="b250b-103">*Multiplicidad de extremo de asociación* define el número de [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) instancias que pueden estar en un extremo de un [asociación](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="b250b-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="b250b-104">Una multiplicidad de extremo de asociación puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="b250b-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="b250b-105">uno (1): Indica que esa instancia de tipo exactamente una entidad existe en el extremo de asociación.</span><span class="sxs-lookup"><span data-stu-id="b250b-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="b250b-106">cero o uno (de 0.. 1): Indica que hay cero o una instancia de tipo de entidad en el extremo de asociación.</span><span class="sxs-lookup"><span data-stu-id="b250b-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="b250b-107">muchos (\*): indica que el cero, uno o más instancias del tipo de entidad existen en el extremo de asociación.</span><span class="sxs-lookup"><span data-stu-id="b250b-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="b250b-108">Normalmente, una asociación se caracteriza por sus multiplicidades de extremo de asociación.</span><span class="sxs-lookup"><span data-stu-id="b250b-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="b250b-109">Por ejemplo, si los extremos de una asociación tienen multiplicidades uno (1) y varios (\*), la asociación se denomina una asociación uno a varios.</span><span class="sxs-lookup"><span data-stu-id="b250b-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="b250b-110">En el ejemplo siguiente, la asociación `PublishedBy` es una asociación uno a varios (un publicador publica muchos libros y un libro solo puede ser publicado por un publicador).</span><span class="sxs-lookup"><span data-stu-id="b250b-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="b250b-111">La asociación `WrittenBy` es una asociación varios a varios (un libro puede tener varios autores y un autor puede escribir varios libros).</span><span class="sxs-lookup"><span data-stu-id="b250b-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b250b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b250b-112">Example</span></span>  
 <span data-ttu-id="b250b-113">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="b250b-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="b250b-114">Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="b250b-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="b250b-115">La multiplicidad de la `Publisher` final es uno (1) y la multiplicidad de la `Book` final es igual a many (\*).</span><span class="sxs-lookup"><span data-stu-id="b250b-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="b250b-117">ADO.NET Entity Framework usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="b250b-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="b250b-118">El código CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior:</span><span class="sxs-lookup"><span data-stu-id="b250b-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b250b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b250b-119">See also</span></span>

- [<span data-ttu-id="b250b-120">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b250b-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="b250b-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b250b-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
