---
title: Procedimiento para consultar información
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166409"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="ae816-102">Procedimiento para consultar información</span><span class="sxs-lookup"><span data-stu-id="ae816-102">How to: Query for Information</span></span>

<span data-ttu-id="ae816-103">Las consultas de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usan la misma sintaxis que las consultas de Linq.</span><span class="sxs-lookup"><span data-stu-id="ae816-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="ae816-104">La única diferencia es que los objetos a los que se hace referencia en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las consultas se asignan a los elementos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="ae816-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="ae816-105">Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ae816-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ae816-106">convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ae816-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="ae816-107">Algunas características de las consultas LINQ pueden necesitar especial atención en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ae816-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="ae816-108">Para obtener más información, vea [conceptos de consultas](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="ae816-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae816-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae816-109">Example</span></span>  

 <span data-ttu-id="ae816-110">La consulta siguiente solicita una lista de clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="ae816-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="ae816-111">En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="ae816-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ae816-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae816-112">See also</span></span>

- [<span data-ttu-id="ae816-113">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="ae816-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="ae816-114">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae816-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="ae816-115">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="ae816-115">Querying the Database</span></span>](querying-the-database.md)
