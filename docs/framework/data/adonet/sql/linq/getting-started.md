---
title: Introducción
description: Con este código de ejemplo, empiece a usar LINQ to SQL para usar la tecnología LINQ para tener acceso a las bases de datos SQL tal como lo haría con una colección en memoria.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: b886518d4cff687a18f363c3e3ba43b40631a22f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194380"
---
# <a name="getting-started"></a><span data-ttu-id="1bde1-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="1bde1-103">Getting Started</span></span>

<span data-ttu-id="1bde1-104">Mediante el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , puede usar la tecnología LINQ para tener acceso a las bases de datos SQL de la misma forma que tendría acceso a una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="1bde1-104">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="1bde1-105">Por ejemplo, en el código siguiente, se crea el objeto `nw` para representar la base de datos `Northwind`, el destino es la tabla `Customers`, las filas se filtran para `Customers` de `London` y se selecciona para la recuperación una cadena de `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="1bde1-105">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="1bde1-106">Cuando se ejecuta el bucle, se recupera la colección de valores `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="1bde1-106">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="1bde1-107">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1bde1-107">Next Steps</span></span>  

 <span data-ttu-id="1bde1-108">Para ver algunos ejemplos adicionales, como la inserción y la actualización, consulte [lo que puede hacer con LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1bde1-108">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="1bde1-109">Luego, intente realizar algunos tutoriales para obtener experiencia práctica en el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bde1-109">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="1bde1-110">Vea [aprendizaje de los tutoriales](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="1bde1-110">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="1bde1-111">Por último, aprenda a empezar a trabajar en su propio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto mediante la lectura de [los pasos típicos para usar LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1bde1-111">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bde1-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bde1-112">See also</span></span>

- [<span data-ttu-id="1bde1-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1bde1-113">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="1bde1-114">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="1bde1-114">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="1bde1-115">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bde1-115">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="1bde1-116">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1bde1-116">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
