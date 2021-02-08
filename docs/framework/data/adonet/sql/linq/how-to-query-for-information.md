---
description: 'Más información acerca de cómo: consultar información'
title: Procedimiento para consultar información
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 41774834fe919b28d71691203941cb8e0a8a0397
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802026"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="837c6-103">Procedimiento para consultar información</span><span class="sxs-lookup"><span data-stu-id="837c6-103">How to: Query for Information</span></span>

<span data-ttu-id="837c6-104">Las consultas de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usan la misma sintaxis que las consultas de Linq.</span><span class="sxs-lookup"><span data-stu-id="837c6-104">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="837c6-105">La única diferencia es que los objetos a los que se hace referencia en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las consultas se asignan a los elementos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="837c6-105">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="837c6-106">Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="837c6-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="837c6-107">convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="837c6-107">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="837c6-108">Algunas características de las consultas LINQ pueden necesitar especial atención en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="837c6-108">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="837c6-109">Para obtener más información, vea [conceptos de consultas](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="837c6-109">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="837c6-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="837c6-110">Example</span></span>  

 <span data-ttu-id="837c6-111">La consulta siguiente solicita una lista de clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="837c6-111">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="837c6-112">En este ejemplo, `Customers` es una tabla de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="837c6-112">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="837c6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="837c6-113">See also</span></span>

- [<span data-ttu-id="837c6-114">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="837c6-114">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="837c6-115">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="837c6-115">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="837c6-116">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="837c6-116">Querying the Database</span></span>](querying-the-database.md)
