---
title: Tipos estructurados que aceptan valores NULL [Entity SQL]
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 632b092e1d0d99a2a40cc3cd4b323e234de6232b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127860"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="9fc7f-102">Tipos estructurados que aceptan valores NULL [Entity SQL]</span><span class="sxs-lookup"><span data-stu-id="9fc7f-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="9fc7f-103">Una instancia `null` de un tipo estructurado es una instancia que no existe.</span><span class="sxs-lookup"><span data-stu-id="9fc7f-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="9fc7f-104">Es diferente de una instancia existente en la que todas las propiedades tienen valores `null`.</span><span class="sxs-lookup"><span data-stu-id="9fc7f-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="9fc7f-105">En este tema se describen los tipos estructurados que admiten valores NULL, incluidos los que admiten valores NULL cuyos patrones de código producen instancias de `null` de tipos que admiten valores NULL estructurados.</span><span class="sxs-lookup"><span data-stu-id="9fc7f-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="9fc7f-106">Modalidad de tipos estructurados que admiten valores NULL</span><span class="sxs-lookup"><span data-stu-id="9fc7f-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="9fc7f-107">Hay tres modalidades de tipos de estructura que admiten valores NULL:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="9fc7f-108">Tipos de fila.</span><span class="sxs-lookup"><span data-stu-id="9fc7f-108">Row types.</span></span>  
  
-   <span data-ttu-id="9fc7f-109">Tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="9fc7f-109">Complex types.</span></span>  
  
-   <span data-ttu-id="9fc7f-110">Tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="9fc7f-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="9fc7f-111">Patrones de código que generan instancias NULL de tipos estructurados</span><span class="sxs-lookup"><span data-stu-id="9fc7f-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="9fc7f-112">Las escenarios siguientes producen instancias `null`:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="9fc7f-113">Dar forma a `null` como un tipo estructurado:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="9fc7f-114">Convertir un tipo base en un tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="9fc7f-115">Unión externa en una condición falsa:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9fc7f-116">O bien</span><span class="sxs-lookup"><span data-stu-id="9fc7f-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9fc7f-117">O bien</span><span class="sxs-lookup"><span data-stu-id="9fc7f-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="9fc7f-118">Desreferenciar `null`:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="9fc7f-119">Obtener ANYELEMENT de una colección vacía:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="9fc7f-120">Comprobar instancias `null` de tipos estructurados:</span><span class="sxs-lookup"><span data-stu-id="9fc7f-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9fc7f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fc7f-121">See also</span></span>

- [<span data-ttu-id="9fc7f-122">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9fc7f-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
