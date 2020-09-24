---
title: función definida por el modelo
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 04d27387c30d5fe09d31c1b2cc94741f21ffe8e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150783"
---
# <a name="model-defined-function"></a><span data-ttu-id="87139-102">función definida por el modelo</span><span class="sxs-lookup"><span data-stu-id="87139-102">model-defined function</span></span>

<span data-ttu-id="87139-103">Una *función definida por el modelo* es una función que se define en un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="87139-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="87139-104">El cuerpo de una función definida por el modelo se expresa en [Entity SQL](./ef/language-reference/entity-sql-language.md), lo que permite expresar la función independientemente de las reglas o los lenguajes admitidos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="87139-104">The body of a model-defined function is expressed in [Entity SQL](./ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="87139-105">La definición para una función definida por el modelo contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="87139-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="87139-106">Un nombre de función.</span><span class="sxs-lookup"><span data-stu-id="87139-106">A function name.</span></span> <span data-ttu-id="87139-107">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="87139-107">(Required)</span></span>  
  
- <span data-ttu-id="87139-108">El tipo del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="87139-108">The type of the return value.</span></span> <span data-ttu-id="87139-109">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="87139-109">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="87139-110">Si no se especifica ningún tipo de valor devuelto, este es void.</span><span class="sxs-lookup"><span data-stu-id="87139-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="87139-111">Información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="87139-111">Parameter information.</span></span> <span data-ttu-id="87139-112">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="87139-112">(Optional)</span></span>  
  
- <span data-ttu-id="87139-113">Expresión [Entity SQL](./ef/language-reference/entity-sql-language.md) que define el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="87139-113">An [Entity SQL](./ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="87139-114">Tenga en cuenta que las funciones definidas por el modelo no admiten parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="87139-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="87139-115">Esta restricción se aplica para que las funciones definidas por el modelo puedan ser compuestas.</span><span class="sxs-lookup"><span data-stu-id="87139-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87139-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87139-116">Example</span></span>  

 <span data-ttu-id="87139-117">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="87139-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Captura de pantalla que muestra un modelo con fecha de publicación.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="87139-119">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="87139-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="87139-120">El código CSDL siguiente define una función en el modelo conceptual que devuelve el número de años transcurridos desde la publicación de una instancia de `Book` (en el diagrama anterior).</span><span class="sxs-lookup"><span data-stu-id="87139-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="87139-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="87139-121">See also</span></span>

- [<span data-ttu-id="87139-122">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="87139-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="87139-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="87139-123">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="87139-124">Entity Data Model: tipos de datos primitivos</span><span class="sxs-lookup"><span data-stu-id="87139-124">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)
