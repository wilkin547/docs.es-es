---
description: Más información acerca de:--(comentario) (Entity SQL)
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 793649177d9e64bead7b8755f35bdb51f53f4dd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724978"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="21fae-103">-- (Comentario) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="21fae-103">-- (Comment) (Entity SQL)</span></span>

<span data-ttu-id="21fae-104">Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios.</span><span class="sxs-lookup"><span data-stu-id="21fae-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="21fae-105">Dos guiones (`--`) inician una línea de comentario.</span><span class="sxs-lookup"><span data-stu-id="21fae-105">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21fae-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21fae-106">Syntax</span></span>  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="21fae-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="21fae-107">Arguments</span></span>  

 `text_of_comment`  
 <span data-ttu-id="21fae-108">Cadena de caracteres que contiene el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="21fae-108">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21fae-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21fae-109">Example</span></span>  

 <span data-ttu-id="21fae-110">En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios.</span><span class="sxs-lookup"><span data-stu-id="21fae-110">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="21fae-111">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="21fae-111">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="21fae-112">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="21fae-112">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="21fae-113">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="21fae-113">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="21fae-114">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="21fae-114">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="21fae-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="21fae-115">See also</span></span>

- [<span data-ttu-id="21fae-116">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="21fae-116">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="21fae-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="21fae-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
