---
title: ADO.NET y LINQ to SQL
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 5dc1796b7fb7036f68c2435325c6a29d381c59f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161586"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="a4612-102">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a4612-102">ADO.NET and LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a4612-103">forma parte de la familia de tecnologías de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a4612-103">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="a4612-104">Se basa en los servicios proporcionados por el modelo de proveedor ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a4612-104">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="a4612-105">Por tanto, puede mezclar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] código con las aplicaciones de ADO.net existentes y migrar las soluciones de ADO.net actuales a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4612-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="a4612-106">La ilustración siguiente proporciona una visión de alto nivel de la relación.</span><span class="sxs-lookup"><span data-stu-id="a4612-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="a4612-107">![LINQ to SQL y ADO.NET](./media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="a4612-107">![LINQ to SQL and ADO.NET](./media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="a4612-108">Conexiones</span><span class="sxs-lookup"><span data-stu-id="a4612-108">Connections</span></span>  

 <span data-ttu-id="a4612-109">Puede proporcionar una conexión ADO.NET existente al crear un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="a4612-109">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="a4612-110">Todas las operaciones realizadas en <xref:System.Data.Linq.DataContext> (incluidas las consultas) utilizan esta conexión proporcionada.</span><span class="sxs-lookup"><span data-stu-id="a4612-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="a4612-111">Si la conexión ya está abierta, la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deja tal cual cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="a4612-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="a4612-112">Siempre puede tener acceso a la conexión y cerrarla usted mismo utilizando la propiedad <xref:System.Data.Linq.DataContext.Connection%2A>, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4612-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="a4612-113">Transacciones</span><span class="sxs-lookup"><span data-stu-id="a4612-113">Transactions</span></span>  

 <span data-ttu-id="a4612-114">Puede proporcionar <xref:System.Data.Linq.DataContext> con su propia transacción de base de datos si la aplicación ya ha iniciado la transacción y desea incluir en ella su <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="a4612-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="a4612-115">El método preferido para realizar transacciones con la .NET Framework es usar el <xref:System.Transactions.TransactionScope> objeto.</span><span class="sxs-lookup"><span data-stu-id="a4612-115">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="a4612-116">Con este enfoque, puede realizar transacciones distribuidas que funcionan entre bases de datos y otros administradores de recursos residentes en memoria.</span><span class="sxs-lookup"><span data-stu-id="a4612-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="a4612-117">Los ámbitos de transacción requieren pocos recursos para iniciarse.</span><span class="sxs-lookup"><span data-stu-id="a4612-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="a4612-118">Se promueven a sí mismos a transacciones distribuidas solo cuando hay varias conexiones en el ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="a4612-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="a4612-119">No puede utilizar este enfoque para todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a4612-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="a4612-120">Por ejemplo, la conexión SqlClient no puede promover las transacciones del sistema cuando funciona en un servidor SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="a4612-120">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="a4612-121">En su lugar, se da de alta automáticamente en una transacción distribuida completa cada vez que detecta que se utiliza un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="a4612-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="a4612-122">Comandos SQL directos</span><span class="sxs-lookup"><span data-stu-id="a4612-122">Direct SQL Commands</span></span>  

 <span data-ttu-id="a4612-123">A veces pueden darse situaciones en las que la capacidad de <xref:System.Data.Linq.DataContext> para realizar consultas o enviar cambios es insuficiente para la tarea especializada que se desea realizar.</span><span class="sxs-lookup"><span data-stu-id="a4612-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="a4612-124">En estas circunstancias, se puede utilizar el método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> para emitir comandos SQL a la base de datos y convertir los resultados de la consulta en objetos.</span><span class="sxs-lookup"><span data-stu-id="a4612-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="a4612-125">Por ejemplo, supongamos que los datos de la clase `Customer` ocupan dos tablas (customer1 y customer2).</span><span class="sxs-lookup"><span data-stu-id="a4612-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="a4612-126">La consulta siguiente devuelve una secuencia de objetos `Customer`:</span><span class="sxs-lookup"><span data-stu-id="a4612-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="a4612-127">Siempre que los nombres de columna de los resultados tabulares coincidan con las propiedades de columna de la clase de entidad, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea los objetos fuera de cualquier consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a4612-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="a4612-128">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4612-128">Parameters</span></span>  

 <span data-ttu-id="a4612-129">El método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> acepta parámetros:</span><span class="sxs-lookup"><span data-stu-id="a4612-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="a4612-130">El código siguiente ejecuta una consulta parametrizada:</span><span class="sxs-lookup"><span data-stu-id="a4612-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="a4612-131">Los parámetros se expresan en el texto de la consulta con la misma notación con llaves que `Console.WriteLine()` y `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="a4612-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="a4612-132">`String.Format()` toma la cadena de consulta proporcionada y sustituye los parámetros entre llaves por nombres de parámetros generados, como `@p0`, `@p1` …, `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="a4612-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4612-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4612-133">See also</span></span>

- [<span data-ttu-id="a4612-134">Información general</span><span class="sxs-lookup"><span data-stu-id="a4612-134">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="a4612-135">Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="a4612-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
