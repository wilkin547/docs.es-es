---
description: 'Más información sobre: tipos estructurados que aceptan valores NULL (Entity SQL)'
title: Tipos estructurados que aceptan valores NULL [Entity SQL]
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: bf303c9cd61fad2c2a8ffedf338bb3a8876db27b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802091"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="bfb23-103">Tipos estructurados que aceptan valores NULL [Entity SQL]</span><span class="sxs-lookup"><span data-stu-id="bfb23-103">Nullable Structured Types (Entity SQL)</span></span>

<span data-ttu-id="bfb23-104">Una instancia `null` de un tipo estructurado es una instancia que no existe.</span><span class="sxs-lookup"><span data-stu-id="bfb23-104">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="bfb23-105">Es diferente de una instancia existente en la que todas las propiedades tienen valores `null`.</span><span class="sxs-lookup"><span data-stu-id="bfb23-105">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="bfb23-106">En este tema se describen los tipos estructurados que admiten valores NULL, incluidos los que admiten valores NULL cuyos patrones de código producen instancias de `null` de tipos que admiten valores NULL estructurados.</span><span class="sxs-lookup"><span data-stu-id="bfb23-106">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="bfb23-107">Modalidad de tipos estructurados que admiten valores NULL</span><span class="sxs-lookup"><span data-stu-id="bfb23-107">Kinds of Nullable Structured Types</span></span>  

 <span data-ttu-id="bfb23-108">Hay tres modalidades de tipos de estructura que admiten valores NULL:</span><span class="sxs-lookup"><span data-stu-id="bfb23-108">There are three kinds of nullable structure types:</span></span>  
  
- <span data-ttu-id="bfb23-109">Tipos de fila.</span><span class="sxs-lookup"><span data-stu-id="bfb23-109">Row types.</span></span>  
  
- <span data-ttu-id="bfb23-110">Tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="bfb23-110">Complex types.</span></span>  
  
- <span data-ttu-id="bfb23-111">Tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="bfb23-111">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="bfb23-112">Patrones de código que generan instancias NULL de tipos estructurados</span><span class="sxs-lookup"><span data-stu-id="bfb23-112">Code Patterns that Produce Null Instances of Structured Types</span></span>  

 <span data-ttu-id="bfb23-113">Las escenarios siguientes producen instancias `null`:</span><span class="sxs-lookup"><span data-stu-id="bfb23-113">The following scenarios produce `null` instances:</span></span>  
  
- <span data-ttu-id="bfb23-114">Dar forma a `null` como un tipo estructurado:</span><span class="sxs-lookup"><span data-stu-id="bfb23-114">Shaping `null` as a structured type:</span></span>  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- <span data-ttu-id="bfb23-115">Convertir un tipo base en un tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="bfb23-115">Upcasting of a base type to a derived type:</span></span>  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- <span data-ttu-id="bfb23-116">Unión externa en una condición falsa:</span><span class="sxs-lookup"><span data-stu-id="bfb23-116">Outer join on false condition:</span></span>  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="bfb23-117">O bien</span><span class="sxs-lookup"><span data-stu-id="bfb23-117">--or</span></span>  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="bfb23-118">O bien</span><span class="sxs-lookup"><span data-stu-id="bfb23-118">--or</span></span>  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- <span data-ttu-id="bfb23-119">Desreferenciar `null`:</span><span class="sxs-lookup"><span data-stu-id="bfb23-119">Dereferencing a `null` reference:</span></span>  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- <span data-ttu-id="bfb23-120">Obtener ANYELEMENT de una colección vacía:</span><span class="sxs-lookup"><span data-stu-id="bfb23-120">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- <span data-ttu-id="bfb23-121">Comprobar instancias `null` de tipos estructurados:</span><span class="sxs-lookup"><span data-stu-id="bfb23-121">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bfb23-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfb23-122">See also</span></span>

- [<span data-ttu-id="bfb23-123">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bfb23-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
