---
title: Introducción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 2358869d90baa82d4d51206b4ec1915a60b9a0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360036"
---
# <a name="getting-started"></a><span data-ttu-id="4aaf5-102">Introducción</span><span class="sxs-lookup"><span data-stu-id="4aaf5-102">Getting Started</span></span>
<span data-ttu-id="4aaf5-103">Mediante el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], puede usar el [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnología para tener acceso a SQL las bases de datos igual que obtendría acceso a una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="4aaf5-104">Por ejemplo, en el código siguiente, se crea el objeto `nw` para representar la base de datos `Northwind`, el destino es la tabla `Customers`, las filas se filtran para `Customers` de `London` y se selecciona para la recuperación una cadena de `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="4aaf5-105">Cuando se ejecuta el bucle, se recupera la colección de valores `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="4aaf5-106">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4aaf5-106">Next Steps</span></span>  
 <span data-ttu-id="4aaf5-107">Para algunos ejemplos adicionales, incluida la inserción y actualización, vea [lo que se puede hacer con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4aaf5-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="4aaf5-108">Luego, intente realizar algunos tutoriales para obtener experiencia práctica en el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4aaf5-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="4aaf5-109">Vea [aprender con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="4aaf5-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="4aaf5-110">Por último, aprenda a empezar a trabajar en su propio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto leyendo [pasos habituales para usar LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4aaf5-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aaf5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aaf5-111">See Also</span></span>  
 [<span data-ttu-id="4aaf5-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4aaf5-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="4aaf5-113">Introducción a LINQ</span><span class="sxs-lookup"><span data-stu-id="4aaf5-113">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [<span data-ttu-id="4aaf5-114">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4aaf5-114">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
