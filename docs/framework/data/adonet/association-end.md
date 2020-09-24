---
title: extremo de asociación
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 00e3a7d855957ae539ea652dc8cde3ed8841dda5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153448"
---
# <a name="association-end"></a><span data-ttu-id="3be90-102">extremo de asociación</span><span class="sxs-lookup"><span data-stu-id="3be90-102">association end</span></span>

<span data-ttu-id="3be90-103">Un *extremo de asociación* identifica el [tipo de entidad](entity-type.md) en un extremo de una [Asociación](association-type.md) y el número de instancias de tipo de entidad que pueden existir en ese extremo de una asociación.</span><span class="sxs-lookup"><span data-stu-id="3be90-103">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="3be90-104">Los extremos de asociación se definen como parte de una asociación, y esta debe tener exactamente dos extremos.</span><span class="sxs-lookup"><span data-stu-id="3be90-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="3be90-105">[Las propiedades de navegación](navigation-property.md) permiten la navegación de un extremo de asociación al otro.</span><span class="sxs-lookup"><span data-stu-id="3be90-105">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="3be90-106">Una definición de extremo de asociación contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="3be90-106">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="3be90-107">Uno de los tipos de entidad implicados en la asociación.</span><span class="sxs-lookup"><span data-stu-id="3be90-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="3be90-108">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="3be90-108">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3be90-109">En una asociación determinada, el tipo de entidad especificado para cada extremo de la asociación puede ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="3be90-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="3be90-110">Esto crea una auto-asociación.</span><span class="sxs-lookup"><span data-stu-id="3be90-110">This creates a self-association.</span></span>  
  
- <span data-ttu-id="3be90-111">Una [multiplicidad de extremo de asociación](association-end-multiplicity.md) que indica el número de instancias de tipo de entidad que pueden estar en un extremo de la asociación.</span><span class="sxs-lookup"><span data-stu-id="3be90-111">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="3be90-112">Una multiplicidad de extremo de asociación puede tener un valor de uno (1), cero o uno (0.. 1) o varios ( \* ).</span><span class="sxs-lookup"><span data-stu-id="3be90-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="3be90-113">Nombre para el extremo de la asociación.</span><span class="sxs-lookup"><span data-stu-id="3be90-113">A name for the association end.</span></span> <span data-ttu-id="3be90-114">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="3be90-114">(Optional)</span></span>  
  
- <span data-ttu-id="3be90-115">Información sobre las operaciones que se realizan en el extremo de la asociación, como por ejemplo la eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="3be90-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="3be90-116">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="3be90-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="3be90-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3be90-117">Example</span></span>  

 <span data-ttu-id="3be90-118">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="3be90-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="3be90-119">Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="3be90-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="3be90-120">La multiplicidad del `Publisher` extremo es uno (1) y la multiplicidad del `Book` extremo es muchos ( \* ), lo que indica que un publicador publica muchos libros y un libro publicado por un publicador.</span><span class="sxs-lookup"><span data-stu-id="3be90-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="3be90-122">El Entity Framework ADO.NET usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="3be90-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="3be90-123">El CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="3be90-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="3be90-124">Tenga en cuenta que el tipo, el nombre y la multiplicidad de cada extremo de la asociación se especifican mediante atributos XML (los atributos `Type`, `Role` y `Multiplicity`, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="3be90-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="3be90-125">La información adicional sobre las operaciones realizadas en un extremo se especifica mediante un elemento XML (el elemento `OnDelete`-).</span><span class="sxs-lookup"><span data-stu-id="3be90-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="3be90-126">En este caso, si se elimina un editor, también se eliminan todos los libros asociados.</span><span class="sxs-lookup"><span data-stu-id="3be90-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="3be90-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3be90-127">See also</span></span>

- [<span data-ttu-id="3be90-128">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3be90-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="3be90-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3be90-129">Entity Data Model</span></span>](entity-data-model.md)
