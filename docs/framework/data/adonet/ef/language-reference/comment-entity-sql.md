---
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 9ad6e38726d0802c3bc2090a4e6f11f008828ee5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197903"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="fdb00-102">-- (Comentario) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fdb00-102">-- (Comment) (Entity SQL)</span></span>

<span data-ttu-id="fdb00-103">Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios.</span><span class="sxs-lookup"><span data-stu-id="fdb00-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="fdb00-104">Dos guiones (`--`) inician una línea de comentario.</span><span class="sxs-lookup"><span data-stu-id="fdb00-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdb00-105">Syntax</span></span>  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdb00-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fdb00-106">Arguments</span></span>  

 `text_of_comment`  
 <span data-ttu-id="fdb00-107">Cadena de caracteres que contiene el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="fdb00-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb00-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb00-108">Example</span></span>  

 <span data-ttu-id="fdb00-109">En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios.</span><span class="sxs-lookup"><span data-stu-id="fdb00-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="fdb00-110">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fdb00-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fdb00-111">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fdb00-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fdb00-112">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fdb00-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fdb00-113">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fdb00-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="fdb00-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdb00-114">See also</span></span>

- [<span data-ttu-id="fdb00-115">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fdb00-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="fdb00-116">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fdb00-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
