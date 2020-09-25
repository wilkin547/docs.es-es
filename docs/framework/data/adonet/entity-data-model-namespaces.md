---
title: 'Entity Data Model: Espacios de nombres'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: 1e5f9527ec208c5650c68fe35bb758e0850b7700
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194835"
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="ff109-102">Entity Data Model: Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="ff109-102">Entity Data Model: Namespaces</span></span>

<span data-ttu-id="ff109-103">Un espacio de nombres en el Entity Data Model (EDM) es un contenedor abstracto para [tipos de entidad](entity-type.md), [tipos complejos](complex-type.md)y [asociaciones](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="ff109-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](entity-type.md), [complex types](complex-type.md), and [associations](association-type.md).</span></span> <span data-ttu-id="ff109-104">Los espacios de nombres en EDM son similares a los de un lenguaje de programación: proporcionan el contexto para los objetos que contienen, así como una manera de eliminar la ambigüedad de objetos que tienen el mismo nombre (pero que contienen espacios de nombres diferentes).</span><span class="sxs-lookup"><span data-stu-id="ff109-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff109-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff109-105">Example</span></span>  

 <span data-ttu-id="ff109-106">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="ff109-106">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="ff109-107">En el siguiente código CSDL se utiliza un espacio de nombres para identificar un tipo que se define en un modelo conceptual diferente.</span><span class="sxs-lookup"><span data-stu-id="ff109-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="ff109-108">En el ejemplo se define un tipo de entidad (`Publisher`) con una propiedad de tipo complejo (`Address`) que se importa del espacio de nombres `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="ff109-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="ff109-109">Observe que el elemento `Using` indica que se ha importado un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ff109-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="ff109-110">Observe también que el tipo de la propiedad `Address` se define utilizando su nombre completo (`ExtendedBooksModel.Address`), lo que indica que este tipo se define en el espacio de nombres `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="ff109-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="ff109-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff109-111">See also</span></span>

- [<span data-ttu-id="ff109-112">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ff109-112">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="ff109-113">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ff109-113">Entity Data Model</span></span>](entity-data-model.md)
