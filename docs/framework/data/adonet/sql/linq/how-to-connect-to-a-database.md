---
title: Procedimiento para conectar a una base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: 48ff4af2c881104d5699910e20ef86eea0466d2a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793863"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="bd056-102">Procedimiento para conectar a una base de datos</span><span class="sxs-lookup"><span data-stu-id="bd056-102">How to: Connect to a Database</span></span>
<span data-ttu-id="bd056-103"><xref:System.Data.Linq.DataContext> es la canalización principal mediante la cual se conecta a una base de datos, recupera los objetos de ella y le vuelve a enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bd056-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="bd056-104">Puede usar el <xref:System.Data.Linq.DataContext> mismo modo que usaría un ADO.net. <xref:System.Data.SqlClient.SqlConnection></span><span class="sxs-lookup"><span data-stu-id="bd056-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="bd056-105">De hecho, <xref:System.Data.Linq.DataContext> se inicializa con la conexión o cadena de conexión que proporcione.</span><span class="sxs-lookup"><span data-stu-id="bd056-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="bd056-106">Para obtener más información, vea [métodos DataContext (Object](/visualstudio/data-tools/datacontext-methods-o-r-designer)Relational Designer).</span><span class="sxs-lookup"><span data-stu-id="bd056-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="bd056-107">El propósito de <xref:System.Data.Linq.DataContext> es convertir sus solicitudes de objetos en consultas SQL que se van a ejecutar en la base de datos y, a continuación, ensamblar los objetos a partir de los resultados.</span><span class="sxs-lookup"><span data-stu-id="bd056-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="bd056-108"><xref:System.Data.Linq.DataContext> habilita [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] al implementar el mismo patrón de operador que los operadores de consulta estándar, como `Where` y `Select`.</span><span class="sxs-lookup"><span data-stu-id="bd056-108">The <xref:System.Data.Linq.DataContext> enables [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bd056-109">Es fundamental mantener una conexión segura.</span><span class="sxs-lookup"><span data-stu-id="bd056-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="bd056-110">Para obtener más información, consulte [seguridad en LINQ to SQL](security-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bd056-110">For more information, see [Security in LINQ to SQL](security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd056-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd056-111">Example</span></span>  
 <span data-ttu-id="bd056-112">En el ejemplo siguiente, se utiliza <xref:System.Data.Linq.DataContext> para establecer una conexión con la base de datos de ejemplo Northwind y recuperar las filas de clientes cuya ciudad es Londres (London).</span><span class="sxs-lookup"><span data-stu-id="bd056-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="bd056-113">Cada tabla de base de datos se representa como una colección `Table` disponible a través del método <xref:System.Data.Linq.DataContext.GetTable%2A>, utilizando la clase de entidad para su identificación.</span><span class="sxs-lookup"><span data-stu-id="bd056-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd056-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd056-114">Example</span></span>  
 <span data-ttu-id="bd056-115">El procedimiento recomendado es declarar un <xref:System.Data.Linq.DataContext> fuertemente tipado en lugar de confiar en la clase <xref:System.Data.Linq.DataContext> básica y el método <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd056-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="bd056-116">Un <xref:System.Data.Linq.DataContext> fuertemente tipado declara todas las colecciones `Table` como miembros del contexto, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd056-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="bd056-117">Después, puede expresar la consulta de clientes de Londres de manera más sencilla:</span><span class="sxs-lookup"><span data-stu-id="bd056-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="bd056-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd056-118">See also</span></span>

- [<span data-ttu-id="bd056-119">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="bd056-119">Communicating with the Database</span></span>](communicating-with-the-database.md)
