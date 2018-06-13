---
title: Transacciones y simultaneidad
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 9ea136a34c478f3619c81ad3cbbae0765fb99374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365272"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="66892-102">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="66892-102">Transactions and Concurrency</span></span>
<span data-ttu-id="66892-103">Una transacción consiste en un comando único o en un grupo de comandos que se ejecutan como un paquete.</span><span class="sxs-lookup"><span data-stu-id="66892-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="66892-104">Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="66892-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="66892-105">Si en un punto de la transacción se produjera un error, todas las actualizaciones podrían revertirse y devolverse al estado que tenían antes de la transacción.</span><span class="sxs-lookup"><span data-stu-id="66892-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="66892-106">Una transacción debe ajustarse a las propiedades ACID (atomicidad, coherencia, aislamiento y durabilidad) para poder garantizar la coherencia de datos.</span><span class="sxs-lookup"><span data-stu-id="66892-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="66892-107">La mayoría de los sistemas de bases de datos relacionales, como Microsoft SQL Server, admiten transacciones, al proporcionar funciones de bloqueo, registro y administración de transacciones cada vez que una aplicación cliente realiza una operación de actualización, inserción o eliminación.</span><span class="sxs-lookup"><span data-stu-id="66892-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66892-108">Las transacciones que requieren varios recursos pueden reducir la simultaneidad si la duración del bloqueo es demasiado larga.</span><span class="sxs-lookup"><span data-stu-id="66892-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="66892-109">Por ello, haga la transacción lo más corta posible.</span><span class="sxs-lookup"><span data-stu-id="66892-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="66892-110">Las transacciones explícitas en procedimientos almacenados suelen dar mejores resultados cuando una transacción implica el uso de varias tablas en la misma base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="66892-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="66892-111">Se pueden crear transacciones en procedimientos almacenados de SQL Server mediante las instrucciones `BEGIN TRANSACTION`, `COMMIT TRANSACTION` o `ROLLBACK TRANSACTION` de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="66892-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="66892-112">Para obtener más información, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66892-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="66892-113">Las transacciones que implican a varios administradores de recursos, como un a transacción entre SQL Server y Oracle, requieren una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="66892-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66892-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="66892-114">In This Section</span></span>  
 [<span data-ttu-id="66892-115">Transacciones locales</span><span class="sxs-lookup"><span data-stu-id="66892-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="66892-116">Muestra cómo realizar transacciones en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="66892-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="66892-117">Transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="66892-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="66892-118">Describe cómo realizar transacciones distribuidas en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="66892-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="66892-119">Integración de System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="66892-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="66892-120">Describe <xref:System.Transactions> integración con SQL Server para trabajar con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="66892-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="66892-121">Simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="66892-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="66892-122">Describe la simultaneidad optimista y pesimista, y cómo puede probar las infracciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="66892-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66892-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="66892-123">See Also</span></span>  
 [<span data-ttu-id="66892-124">Principios de la transacción</span><span class="sxs-lookup"><span data-stu-id="66892-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [<span data-ttu-id="66892-125">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="66892-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="66892-126">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="66892-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="66892-127">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="66892-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="66892-128">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="66892-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="66892-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="66892-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
