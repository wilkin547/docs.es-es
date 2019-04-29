---
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606002"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="c5d0e-102">-- (Comentario) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c5d0e-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="c5d0e-103">Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios.</span><span class="sxs-lookup"><span data-stu-id="c5d0e-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="c5d0e-104">Dos guiones (`--`) inician una línea de comentario.</span><span class="sxs-lookup"><span data-stu-id="c5d0e-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5d0e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5d0e-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5d0e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c5d0e-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="c5d0e-107">Cadena de caracteres que contiene el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="c5d0e-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5d0e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5d0e-108">Example</span></span>  
 <span data-ttu-id="c5d0e-109">En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios.</span><span class="sxs-lookup"><span data-stu-id="c5d0e-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="c5d0e-110">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c5d0e-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c5d0e-111">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c5d0e-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c5d0e-112">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c5d0e-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c5d0e-113">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c5d0e-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="c5d0e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5d0e-114">See also</span></span>

- [<span data-ttu-id="c5d0e-115">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c5d0e-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="c5d0e-116">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c5d0e-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
