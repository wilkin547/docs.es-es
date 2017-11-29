---
title: "función definida por el modelo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8e311d6e9c67a30636bdeaea7982057605678684
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="model-defined-function"></a><span data-ttu-id="06bd7-102">función definida por el modelo</span><span class="sxs-lookup"><span data-stu-id="06bd7-102">model-defined function</span></span>
<span data-ttu-id="06bd7-103">A *función definida por el modelo* es una función que se define en un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="06bd7-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="06bd7-104">El cuerpo de una función definida por el modelo se expresa en [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), lo que permite la función se exprese independientemente de las reglas o lenguajes admitidos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="06bd7-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="06bd7-105">La definición para una función definida por el modelo contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="06bd7-105">A definition for a model-defined function contains the following information:</span></span>  
  
-   <span data-ttu-id="06bd7-106">El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="06bd7-106">A function name.</span></span> <span data-ttu-id="06bd7-107">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="06bd7-107">(Required)</span></span>  
  
-   <span data-ttu-id="06bd7-108">El tipo del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="06bd7-108">The type of the return value.</span></span> <span data-ttu-id="06bd7-109">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="06bd7-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06bd7-110">Si no se especifica ningún tipo de valor devuelto, este es void.</span><span class="sxs-lookup"><span data-stu-id="06bd7-110">If no return type is specified, the return value is void.</span></span>  
  
-   <span data-ttu-id="06bd7-111">Información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="06bd7-111">Parameter information.</span></span> <span data-ttu-id="06bd7-112">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="06bd7-112">(Optional)</span></span>  
  
-   <span data-ttu-id="06bd7-113">Un [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expresión que define el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="06bd7-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="06bd7-114">Tenga en cuenta que las funciones definidas por el modelo no admiten parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="06bd7-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="06bd7-115">Esta restricción se aplica para que las funciones definidas por el modelo puedan ser compuestas.</span><span class="sxs-lookup"><span data-stu-id="06bd7-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06bd7-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06bd7-116">Example</span></span>  
 <span data-ttu-id="06bd7-117">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="06bd7-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="06bd7-118">![Modelar con fecha de publicación](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span><span class="sxs-lookup"><span data-stu-id="06bd7-118">![Model With Published Date](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span></span>  
  
 <span data-ttu-id="06bd7-119">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="06bd7-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="06bd7-120">El código CSDL siguiente define una función en el modelo conceptual que devuelve el número de años transcurridos desde la publicación de una instancia de `Book` (en el diagrama anterior).</span><span class="sxs-lookup"><span data-stu-id="06bd7-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="06bd7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="06bd7-121">See Also</span></span>  
 [<span data-ttu-id="06bd7-122">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="06bd7-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="06bd7-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="06bd7-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="06bd7-124">Entity Data Model: Tipos de datos primitivos</span><span class="sxs-lookup"><span data-stu-id="06bd7-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
