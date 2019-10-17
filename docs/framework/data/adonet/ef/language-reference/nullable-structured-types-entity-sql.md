---
title: Tipos estructurados que aceptan valores NULL [Entity SQL]
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: b155c672d8c0bef8b01fb26fb49908f094add25a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319486"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="4fa72-102">Tipos estructurados que aceptan valores NULL [Entity SQL]</span><span class="sxs-lookup"><span data-stu-id="4fa72-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="4fa72-103">Una instancia `null` de un tipo estructurado es una instancia que no existe.</span><span class="sxs-lookup"><span data-stu-id="4fa72-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="4fa72-104">Es diferente de una instancia existente en la que todas las propiedades tienen valores `null`.</span><span class="sxs-lookup"><span data-stu-id="4fa72-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="4fa72-105">En este tema se describen los tipos estructurados que admiten valores NULL, incluidos los que admiten valores NULL cuyos patrones de código producen instancias de `null` de tipos que admiten valores NULL estructurados.</span><span class="sxs-lookup"><span data-stu-id="4fa72-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="4fa72-106">Modalidad de tipos estructurados que admiten valores NULL</span><span class="sxs-lookup"><span data-stu-id="4fa72-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="4fa72-107">Hay tres modalidades de tipos de estructura que admiten valores NULL:</span><span class="sxs-lookup"><span data-stu-id="4fa72-107">There are three kinds of nullable structure types:</span></span>  
  
- <span data-ttu-id="4fa72-108">Tipos de fila.</span><span class="sxs-lookup"><span data-stu-id="4fa72-108">Row types.</span></span>  
  
- <span data-ttu-id="4fa72-109">Tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="4fa72-109">Complex types.</span></span>  
  
- <span data-ttu-id="4fa72-110">Tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="4fa72-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="4fa72-111">Patrones de código que generan instancias NULL de tipos estructurados</span><span class="sxs-lookup"><span data-stu-id="4fa72-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="4fa72-112">Las escenarios siguientes producen instancias `null`:</span><span class="sxs-lookup"><span data-stu-id="4fa72-112">The following scenarios produce `null` instances:</span></span>  
  
- <span data-ttu-id="4fa72-113">Dar forma a `null` como un tipo estructurado:</span><span class="sxs-lookup"><span data-stu-id="4fa72-113">Shaping `null` as a structured type:</span></span>  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- <span data-ttu-id="4fa72-114">Convertir un tipo base en un tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="4fa72-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- <span data-ttu-id="4fa72-115">Unión externa en una condición falsa:</span><span class="sxs-lookup"><span data-stu-id="4fa72-115">Outer join on false condition:</span></span>  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="4fa72-116">O bien</span><span class="sxs-lookup"><span data-stu-id="4fa72-116">--or</span></span>  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="4fa72-117">O bien</span><span class="sxs-lookup"><span data-stu-id="4fa72-117">--or</span></span>  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- <span data-ttu-id="4fa72-118">Desreferenciar `null`:</span><span class="sxs-lookup"><span data-stu-id="4fa72-118">Dereferencing a `null` reference:</span></span>  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- <span data-ttu-id="4fa72-119">Obtener ANYELEMENT de una colección vacía:</span><span class="sxs-lookup"><span data-stu-id="4fa72-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- <span data-ttu-id="4fa72-120">Comprobar instancias `null` de tipos estructurados:</span><span class="sxs-lookup"><span data-stu-id="4fa72-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4fa72-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fa72-121">See also</span></span>

- [<span data-ttu-id="4fa72-122">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4fa72-122">Entity SQL Overview</span></span>](entity-sql-overview.md)
