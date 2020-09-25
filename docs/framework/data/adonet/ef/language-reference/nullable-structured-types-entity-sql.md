---
title: Tipos estructurados que aceptan valores NULL [Entity SQL]
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: fc2230401ef98c005ab52a845de37482c0dcf698
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202269"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="08ad9-102">Tipos estructurados que aceptan valores NULL [Entity SQL]</span><span class="sxs-lookup"><span data-stu-id="08ad9-102">Nullable Structured Types (Entity SQL)</span></span>

<span data-ttu-id="08ad9-103">Una instancia `null` de un tipo estructurado es una instancia que no existe.</span><span class="sxs-lookup"><span data-stu-id="08ad9-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="08ad9-104">Es diferente de una instancia existente en la que todas las propiedades tienen valores `null`.</span><span class="sxs-lookup"><span data-stu-id="08ad9-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="08ad9-105">En este tema se describen los tipos estructurados que admiten valores NULL, incluidos los que admiten valores NULL cuyos patrones de código producen instancias de `null` de tipos que admiten valores NULL estructurados.</span><span class="sxs-lookup"><span data-stu-id="08ad9-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="08ad9-106">Modalidad de tipos estructurados que admiten valores NULL</span><span class="sxs-lookup"><span data-stu-id="08ad9-106">Kinds of Nullable Structured Types</span></span>  

 <span data-ttu-id="08ad9-107">Hay tres modalidades de tipos de estructura que admiten valores NULL:</span><span class="sxs-lookup"><span data-stu-id="08ad9-107">There are three kinds of nullable structure types:</span></span>  
  
- <span data-ttu-id="08ad9-108">Tipos de fila.</span><span class="sxs-lookup"><span data-stu-id="08ad9-108">Row types.</span></span>  
  
- <span data-ttu-id="08ad9-109">Tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="08ad9-109">Complex types.</span></span>  
  
- <span data-ttu-id="08ad9-110">Tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="08ad9-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="08ad9-111">Patrones de código que generan instancias NULL de tipos estructurados</span><span class="sxs-lookup"><span data-stu-id="08ad9-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  

 <span data-ttu-id="08ad9-112">Las escenarios siguientes producen instancias `null`:</span><span class="sxs-lookup"><span data-stu-id="08ad9-112">The following scenarios produce `null` instances:</span></span>  
  
- <span data-ttu-id="08ad9-113">Dar forma a `null` como un tipo estructurado:</span><span class="sxs-lookup"><span data-stu-id="08ad9-113">Shaping `null` as a structured type:</span></span>  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- <span data-ttu-id="08ad9-114">Convertir un tipo base en un tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="08ad9-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- <span data-ttu-id="08ad9-115">Unión externa en una condición falsa:</span><span class="sxs-lookup"><span data-stu-id="08ad9-115">Outer join on false condition:</span></span>  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="08ad9-116">O bien</span><span class="sxs-lookup"><span data-stu-id="08ad9-116">--or</span></span>  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="08ad9-117">O bien</span><span class="sxs-lookup"><span data-stu-id="08ad9-117">--or</span></span>  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- <span data-ttu-id="08ad9-118">Desreferenciar `null`:</span><span class="sxs-lookup"><span data-stu-id="08ad9-118">Dereferencing a `null` reference:</span></span>  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- <span data-ttu-id="08ad9-119">Obtener ANYELEMENT de una colección vacía:</span><span class="sxs-lookup"><span data-stu-id="08ad9-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- <span data-ttu-id="08ad9-120">Comprobar instancias `null` de tipos estructurados:</span><span class="sxs-lookup"><span data-stu-id="08ad9-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="08ad9-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08ad9-121">See also</span></span>

- [<span data-ttu-id="08ad9-122">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="08ad9-122">Entity SQL Overview</span></span>](entity-sql-overview.md)
