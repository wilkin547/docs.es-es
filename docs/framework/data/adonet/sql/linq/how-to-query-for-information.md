---
title: 'Cómo: Consultar información'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634656"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="b2043-102">Cómo: Consultar información</span><span class="sxs-lookup"><span data-stu-id="b2043-102">How to: Query for Information</span></span>
<span data-ttu-id="b2043-103">Las consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizan la misma sintaxis que las consultas de LINQ.</span><span class="sxs-lookup"><span data-stu-id="b2043-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="b2043-104">La única diferencia es que los objetos a los que se hace referencia en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consultas se asignan a los elementos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b2043-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="b2043-105">Para obtener más información, vea [Introduction to LINQ queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="b2043-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b2043-106">convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b2043-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="b2043-107">Es posible que algunas características de las consultas LINQ necesiten especial atención en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b2043-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="b2043-108">Para obtener más información, vea [conceptos de consultas](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="b2043-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2043-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2043-109">Example</span></span>  
 <span data-ttu-id="b2043-110">La consulta siguiente solicita una lista de clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="b2043-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="b2043-111">En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="b2043-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b2043-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2043-112">See also</span></span>

- [<span data-ttu-id="b2043-113">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="b2043-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="b2043-114">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2043-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="b2043-115">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="b2043-115">Querying the Database</span></span>](querying-the-database.md)
