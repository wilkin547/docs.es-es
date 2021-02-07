---
description: 'Más información sobre: función definida por el modelo'
title: función definida por el modelo
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 146ef4a8ad8c38897b8e56b6bc1485e1e40754cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723743"
---
# <a name="model-defined-function"></a><span data-ttu-id="adc36-103">función definida por el modelo</span><span class="sxs-lookup"><span data-stu-id="adc36-103">model-defined function</span></span>

<span data-ttu-id="adc36-104">Una *función definida por el modelo* es una función que se define en un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="adc36-104">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="adc36-105">El cuerpo de una función definida por el modelo se expresa en [Entity SQL](./ef/language-reference/entity-sql-language.md), lo que permite expresar la función independientemente de las reglas o los lenguajes admitidos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="adc36-105">The body of a model-defined function is expressed in [Entity SQL](./ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="adc36-106">La definición para una función definida por el modelo contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="adc36-106">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="adc36-107">Un nombre de función.</span><span class="sxs-lookup"><span data-stu-id="adc36-107">A function name.</span></span> <span data-ttu-id="adc36-108">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="adc36-108">(Required)</span></span>  
  
- <span data-ttu-id="adc36-109">El tipo del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="adc36-109">The type of the return value.</span></span> <span data-ttu-id="adc36-110">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="adc36-110">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="adc36-111">Si no se especifica ningún tipo de valor devuelto, este es void.</span><span class="sxs-lookup"><span data-stu-id="adc36-111">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="adc36-112">Información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="adc36-112">Parameter information.</span></span> <span data-ttu-id="adc36-113">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="adc36-113">(Optional)</span></span>  
  
- <span data-ttu-id="adc36-114">Expresión [Entity SQL](./ef/language-reference/entity-sql-language.md) que define el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="adc36-114">An [Entity SQL](./ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="adc36-115">Tenga en cuenta que las funciones definidas por el modelo no admiten parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="adc36-115">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="adc36-116">Esta restricción se aplica para que las funciones definidas por el modelo puedan ser compuestas.</span><span class="sxs-lookup"><span data-stu-id="adc36-116">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adc36-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adc36-117">Example</span></span>  

 <span data-ttu-id="adc36-118">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="adc36-118">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Captura de pantalla que muestra un modelo con fecha de publicación.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="adc36-120">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="adc36-120">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="adc36-121">El código CSDL siguiente define una función en el modelo conceptual que devuelve el número de años transcurridos desde la publicación de una instancia de `Book` (en el diagrama anterior).</span><span class="sxs-lookup"><span data-stu-id="adc36-121">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="adc36-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="adc36-122">See also</span></span>

- [<span data-ttu-id="adc36-123">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="adc36-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="adc36-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="adc36-124">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="adc36-125">Entity Data Model: tipos de datos primitivos</span><span class="sxs-lookup"><span data-stu-id="adc36-125">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)
