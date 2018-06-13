---
title: Tipos estructurados que aceptan valores NULL [Entity SQL]
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 6b949cebfa1b16f8e6fb5a133c61c5668d90b3bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762392"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="ae0d6-102">Tipos estructurados que aceptan valores NULL [Entity SQL]</span><span class="sxs-lookup"><span data-stu-id="ae0d6-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="ae0d6-103">Una instancia `null` de un tipo estructurado es una instancia que no existe.</span><span class="sxs-lookup"><span data-stu-id="ae0d6-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="ae0d6-104">Es diferente de una instancia existente en la que todas las propiedades tienen valores `null`.</span><span class="sxs-lookup"><span data-stu-id="ae0d6-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="ae0d6-105">En este tema se describen los tipos estructurados que admiten valores NULL, incluidos los que admiten valores NULL cuyos patrones de código producen instancias de `null` de tipos que admiten valores NULL estructurados.</span><span class="sxs-lookup"><span data-stu-id="ae0d6-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="ae0d6-106">Modalidad de tipos estructurados que admiten valores NULL</span><span class="sxs-lookup"><span data-stu-id="ae0d6-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="ae0d6-107">Hay tres modalidades de tipos de estructura que admiten valores NULL:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="ae0d6-108">Tipos de fila.</span><span class="sxs-lookup"><span data-stu-id="ae0d6-108">Row types.</span></span>  
  
-   <span data-ttu-id="ae0d6-109">Tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="ae0d6-109">Complex types.</span></span>  
  
-   <span data-ttu-id="ae0d6-110">Tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="ae0d6-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="ae0d6-111">Patrones de código que generan instancias NULL de tipos estructurados</span><span class="sxs-lookup"><span data-stu-id="ae0d6-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="ae0d6-112">Las escenarios siguientes producen instancias `null`:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="ae0d6-113">Dar forma a `null` como un tipo estructurado:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="ae0d6-114">Convertir un tipo base en un tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="ae0d6-115">Unión externa en una condición falsa:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="ae0d6-116">O bien</span><span class="sxs-lookup"><span data-stu-id="ae0d6-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="ae0d6-117">O bien</span><span class="sxs-lookup"><span data-stu-id="ae0d6-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="ae0d6-118">Desreferenciar `null`:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="ae0d6-119">Obtener ANYELEMENT de una colección vacía:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="ae0d6-120">Comprobar instancias `null` de tipos estructurados:</span><span class="sxs-lookup"><span data-stu-id="ae0d6-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae0d6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae0d6-121">See Also</span></span>  
 [<span data-ttu-id="ae0d6-122">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ae0d6-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
