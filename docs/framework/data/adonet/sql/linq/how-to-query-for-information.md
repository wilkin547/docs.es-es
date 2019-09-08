---
title: Procedimiento para consultar información
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: ed32bbe7d27357cbed7d77dd235b698a65c0e29e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793537"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="a7074-102">Procedimiento para consultar información</span><span class="sxs-lookup"><span data-stu-id="a7074-102">How to: Query for Information</span></span>
<span data-ttu-id="a7074-103">Las consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizan la misma sintaxis que las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7074-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="a7074-104">La única diferencia es que los objetos a los que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se hace referencia en las consultas se asignan a los elementos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7074-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="a7074-105">Para obtener más información, vea [Introduction to LINQ queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="a7074-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a7074-106">convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a7074-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="a7074-107">Algunas características de las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] podrían requerir una atención especial en las aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7074-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="a7074-108">Para obtener más información, vea [conceptos de consultas](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a7074-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7074-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7074-109">Example</span></span>  
 <span data-ttu-id="a7074-110">La consulta siguiente solicita una lista de clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="a7074-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="a7074-111">En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="a7074-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a7074-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7074-112">See also</span></span>

- [<span data-ttu-id="a7074-113">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="a7074-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="a7074-114">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7074-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="a7074-115">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="a7074-115">Querying the Database</span></span>](querying-the-database.md)
