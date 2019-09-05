---
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 1ea1929b0e6f965f71fbb015ee6795affb3bce7c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251208"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="62fc8-102">-- (Comentario) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="62fc8-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="62fc8-103">Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios.</span><span class="sxs-lookup"><span data-stu-id="62fc8-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="62fc8-104">Dos guiones (`--`) inician una línea de comentario.</span><span class="sxs-lookup"><span data-stu-id="62fc8-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62fc8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62fc8-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="62fc8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="62fc8-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="62fc8-107">Cadena de caracteres que contiene el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="62fc8-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62fc8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62fc8-108">Example</span></span>  
 <span data-ttu-id="62fc8-109">En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios.</span><span class="sxs-lookup"><span data-stu-id="62fc8-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="62fc8-110">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="62fc8-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="62fc8-111">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="62fc8-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="62fc8-112">Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.</span><span class="sxs-lookup"><span data-stu-id="62fc8-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="62fc8-113">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="62fc8-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="62fc8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="62fc8-114">See also</span></span>

- [<span data-ttu-id="62fc8-115">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="62fc8-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="62fc8-116">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="62fc8-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
