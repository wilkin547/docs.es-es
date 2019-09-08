---
title: Introducción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: bd82b7e83149aaa53cf1b240cb79f8747bccba47
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793913"
---
# <a name="getting-started"></a><span data-ttu-id="27a7b-102">Introducción</span><span class="sxs-lookup"><span data-stu-id="27a7b-102">Getting Started</span></span>
<span data-ttu-id="27a7b-103">Mediante el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]uso de, puede usar [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] la tecnología de para tener acceso a las bases de datos SQL de la misma forma que tendría acceso a una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="27a7b-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="27a7b-104">Por ejemplo, en el código siguiente, se crea el objeto `nw` para representar la base de datos `Northwind`, el destino es la tabla `Customers`, las filas se filtran para `Customers` de `London` y se selecciona para la recuperación una cadena de `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="27a7b-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="27a7b-105">Cuando se ejecuta el bucle, se recupera la colección de valores `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="27a7b-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="27a7b-106">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="27a7b-106">Next Steps</span></span>  
 <span data-ttu-id="27a7b-107">Para ver algunos ejemplos adicionales, como la inserción y la actualización, consulte [lo que puede hacer con LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="27a7b-108">Luego, intente realizar algunos tutoriales para obtener experiencia práctica en el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27a7b-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="27a7b-109">Vea [aprendizaje de los tutoriales](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-109">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="27a7b-110">Por último, aprenda a empezar a trabajar en su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] propio proyecto mediante la lectura de [los pasos típicos para usar LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a7b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="27a7b-111">See also</span></span>

- [<span data-ttu-id="27a7b-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="27a7b-112">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="27a7b-113">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="27a7b-113">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="27a7b-114">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27a7b-114">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="27a7b-115">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="27a7b-115">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
