---
title: Filtrar para consultar información
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162847"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="4ad24-102">Filtrar para consultar información</span><span class="sxs-lookup"><span data-stu-id="4ad24-102">How to: Query for Information</span></span>
<span data-ttu-id="4ad24-103">Las consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizan la misma sintaxis que las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ad24-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="4ad24-104">La única diferencia es que hace referencia los objetos en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las consultas se asignan a los elementos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ad24-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="4ad24-105">Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="4ad24-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4ad24-106">Convierte las consultas que escriben en consultas SQL equivalentes y los envía al servidor para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4ad24-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="4ad24-107">Algunas características de las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] podrían requerir una atención especial en las aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ad24-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="4ad24-108">Para obtener más información, consulte [conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="4ad24-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ad24-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ad24-109">Example</span></span>  
 <span data-ttu-id="4ad24-110">La consulta siguiente solicita una lista de clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="4ad24-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="4ad24-111">En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="4ad24-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4ad24-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ad24-112">See also</span></span>

- [<span data-ttu-id="4ad24-113">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="4ad24-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="4ad24-114">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ad24-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="4ad24-115">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="4ad24-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
