---
description: 'Más información acerca de: ADO.NET y LINQ to SQL'
title: ADO.NET y LINQ to SQL
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 1f3f4a50c13af857ecd9f3195c7f431dd46ed3ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712966"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="31cc1-103">ADO.NET y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="31cc1-103">ADO.NET and LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31cc1-104">forma parte de la familia de tecnologías de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="31cc1-104">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="31cc1-105">Se basa en los servicios proporcionados por el modelo de proveedor ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="31cc1-105">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="31cc1-106">Por tanto, puede mezclar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] código con las aplicaciones de ADO.net existentes y migrar las soluciones de ADO.net actuales a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31cc1-106">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="31cc1-107">La ilustración siguiente proporciona una visión de alto nivel de la relación.</span><span class="sxs-lookup"><span data-stu-id="31cc1-107">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="31cc1-108">![LINQ to SQL y ADO.NET](./media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="31cc1-108">![LINQ to SQL and ADO.NET](./media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="31cc1-109">Conexiones</span><span class="sxs-lookup"><span data-stu-id="31cc1-109">Connections</span></span>  

 <span data-ttu-id="31cc1-110">Puede proporcionar una conexión ADO.NET existente al crear un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="31cc1-110">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="31cc1-111">Todas las operaciones realizadas en <xref:System.Data.Linq.DataContext> (incluidas las consultas) utilizan esta conexión proporcionada.</span><span class="sxs-lookup"><span data-stu-id="31cc1-111">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="31cc1-112">Si la conexión ya está abierta, la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deja tal cual cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="31cc1-112">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="31cc1-113">Siempre puede tener acceso a la conexión y cerrarla usted mismo utilizando la propiedad <xref:System.Data.Linq.DataContext.Connection%2A>, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="31cc1-113">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="31cc1-114">Transacciones</span><span class="sxs-lookup"><span data-stu-id="31cc1-114">Transactions</span></span>  

 <span data-ttu-id="31cc1-115">Puede proporcionar <xref:System.Data.Linq.DataContext> con su propia transacción de base de datos si la aplicación ya ha iniciado la transacción y desea incluir en ella su <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="31cc1-115">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="31cc1-116">El método preferido para realizar transacciones con la .NET Framework es usar el <xref:System.Transactions.TransactionScope> objeto.</span><span class="sxs-lookup"><span data-stu-id="31cc1-116">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="31cc1-117">Con este enfoque, puede realizar transacciones distribuidas que funcionan entre bases de datos y otros administradores de recursos residentes en memoria.</span><span class="sxs-lookup"><span data-stu-id="31cc1-117">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="31cc1-118">Los ámbitos de transacción requieren pocos recursos para iniciarse.</span><span class="sxs-lookup"><span data-stu-id="31cc1-118">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="31cc1-119">Se promueven a sí mismos a transacciones distribuidas solo cuando hay varias conexiones en el ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="31cc1-119">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="31cc1-120">No puede utilizar este enfoque para todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="31cc1-120">You cannot use this approach for all databases.</span></span> <span data-ttu-id="31cc1-121">Por ejemplo, la conexión SqlClient no puede promover las transacciones del sistema cuando funciona en un servidor SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="31cc1-121">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="31cc1-122">En su lugar, se da de alta automáticamente en una transacción distribuida completa cada vez que detecta que se utiliza un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="31cc1-122">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="31cc1-123">Comandos SQL directos</span><span class="sxs-lookup"><span data-stu-id="31cc1-123">Direct SQL Commands</span></span>  

 <span data-ttu-id="31cc1-124">A veces pueden darse situaciones en las que la capacidad de <xref:System.Data.Linq.DataContext> para realizar consultas o enviar cambios es insuficiente para la tarea especializada que se desea realizar.</span><span class="sxs-lookup"><span data-stu-id="31cc1-124">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="31cc1-125">En estas circunstancias, se puede utilizar el método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> para emitir comandos SQL a la base de datos y convertir los resultados de la consulta en objetos.</span><span class="sxs-lookup"><span data-stu-id="31cc1-125">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="31cc1-126">Por ejemplo, supongamos que los datos de la clase `Customer` ocupan dos tablas (customer1 y customer2).</span><span class="sxs-lookup"><span data-stu-id="31cc1-126">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="31cc1-127">La consulta siguiente devuelve una secuencia de objetos `Customer`:</span><span class="sxs-lookup"><span data-stu-id="31cc1-127">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="31cc1-128">Siempre que los nombres de columna de los resultados tabulares coincidan con las propiedades de columna de la clase de entidad, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea los objetos fuera de cualquier consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="31cc1-128">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="31cc1-129">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31cc1-129">Parameters</span></span>  

 <span data-ttu-id="31cc1-130">El método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> acepta parámetros:</span><span class="sxs-lookup"><span data-stu-id="31cc1-130">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="31cc1-131">El código siguiente ejecuta una consulta parametrizada:</span><span class="sxs-lookup"><span data-stu-id="31cc1-131">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="31cc1-132">Los parámetros se expresan en el texto de la consulta con la misma notación con llaves que `Console.WriteLine()` y `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="31cc1-132">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="31cc1-133">`String.Format()` toma la cadena de consulta proporcionada y sustituye los parámetros entre llaves por nombres de parámetros generados, como `@p0`, `@p1` …, `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="31cc1-133">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cc1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="31cc1-134">See also</span></span>

- [<span data-ttu-id="31cc1-135">Información general</span><span class="sxs-lookup"><span data-stu-id="31cc1-135">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="31cc1-136">Procedimiento para reutilizar una conexión entre un comando de ADO.NET y un objeto DataContext</span><span class="sxs-lookup"><span data-stu-id="31cc1-136">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
