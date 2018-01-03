---
title: "Cómo: Conectarse a una base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d03dc5a3775ee9396573d58637c32f824760768f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="a1bce-102">Cómo: Conectarse a una base de datos</span><span class="sxs-lookup"><span data-stu-id="a1bce-102">How to: Connect to a Database</span></span>
<span data-ttu-id="a1bce-103"><xref:System.Data.Linq.DataContext> es la canalización principal mediante la cual se conecta a una base de datos, recupera los objetos de ella y le vuelve a enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a1bce-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="a1bce-104">Usa el <xref:System.Data.Linq.DataContext> tal y como se usaría un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="a1bce-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="a1bce-105">De hecho, <xref:System.Data.Linq.DataContext> se inicializa con la conexión o cadena de conexión que proporcione.</span><span class="sxs-lookup"><span data-stu-id="a1bce-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="a1bce-106">Para obtener más información, consulte [métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="a1bce-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="a1bce-107">El propósito de <xref:System.Data.Linq.DataContext> es convertir sus solicitudes de objetos en consultas SQL que se van a ejecutar en la base de datos y, a continuación, ensamblar los objetos a partir de los resultados.</span><span class="sxs-lookup"><span data-stu-id="a1bce-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="a1bce-108"><xref:System.Data.Linq.DataContext> habilita [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] al implementar el mismo patrón de operador que los operadores de consulta estándar, como `Where` y `Select`.</span><span class="sxs-lookup"><span data-stu-id="a1bce-108">The <xref:System.Data.Linq.DataContext> enables [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a1bce-109">Es fundamental mantener una conexión segura.</span><span class="sxs-lookup"><span data-stu-id="a1bce-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="a1bce-110">Para obtener más información, consulte [seguridad en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a1bce-110">For more information, see [Security in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1bce-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1bce-111">Example</span></span>  
 <span data-ttu-id="a1bce-112">En el ejemplo siguiente, se utiliza <xref:System.Data.Linq.DataContext> para establecer una conexión con la base de datos de ejemplo Northwind y recuperar las filas de clientes cuya ciudad es Londres (London).</span><span class="sxs-lookup"><span data-stu-id="a1bce-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="a1bce-113">Cada tabla de base de datos se representa como una colección `Table` disponible a través del método <xref:System.Data.Linq.DataContext.GetTable%2A>, utilizando la clase de entidad para su identificación.</span><span class="sxs-lookup"><span data-stu-id="a1bce-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1bce-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1bce-114">Example</span></span>  
 <span data-ttu-id="a1bce-115">El procedimiento recomendado es declarar un <xref:System.Data.Linq.DataContext> fuertemente tipado en lugar de confiar en la clase <xref:System.Data.Linq.DataContext> básica y el método <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1bce-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="a1bce-116">Un <xref:System.Data.Linq.DataContext> fuertemente tipado declara todas las colecciones `Table` como miembros del contexto, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1bce-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="a1bce-117">Después, puede expresar la consulta de clientes de Londres de manera más sencilla:</span><span class="sxs-lookup"><span data-stu-id="a1bce-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a1bce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1bce-118">See Also</span></span>  
 [<span data-ttu-id="a1bce-119">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="a1bce-119">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
