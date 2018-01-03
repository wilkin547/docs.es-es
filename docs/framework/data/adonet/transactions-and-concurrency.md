---
title: Transacciones y simultaneidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4301a232e2b38d44ecb288e76439742f7fe4d58f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="37ffc-102">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="37ffc-102">Transactions and Concurrency</span></span>
<span data-ttu-id="37ffc-103">Una transacción consiste en un comando único o en un grupo de comandos que se ejecutan como un paquete.</span><span class="sxs-lookup"><span data-stu-id="37ffc-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="37ffc-104">Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37ffc-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="37ffc-105">Si en un punto de la transacción se produjera un error, todas las actualizaciones podrían revertirse y devolverse al estado que tenían antes de la transacción.</span><span class="sxs-lookup"><span data-stu-id="37ffc-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="37ffc-106">Una transacción debe ajustarse a las propiedades ACID (atomicidad, coherencia, aislamiento y durabilidad) para poder garantizar la coherencia de datos.</span><span class="sxs-lookup"><span data-stu-id="37ffc-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="37ffc-107">La mayoría de los sistemas de bases de datos relacionales, como Microsoft SQL Server, admiten transacciones, al proporcionar funciones de bloqueo, registro y administración de transacciones cada vez que una aplicación cliente realiza una operación de actualización, inserción o eliminación.</span><span class="sxs-lookup"><span data-stu-id="37ffc-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37ffc-108">Las transacciones que requieren varios recursos pueden reducir la simultaneidad si la duración del bloqueo es demasiado larga.</span><span class="sxs-lookup"><span data-stu-id="37ffc-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="37ffc-109">Por ello, haga la transacción lo más corta posible.</span><span class="sxs-lookup"><span data-stu-id="37ffc-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="37ffc-110">Las transacciones explícitas en procedimientos almacenados suelen dar mejores resultados cuando una transacción implica el uso de varias tablas en la misma base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="37ffc-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="37ffc-111">Se pueden crear transacciones en procedimientos almacenados de SQL Server mediante las instrucciones `BEGIN TRANSACTION`, `COMMIT TRANSACTION` o `ROLLBACK TRANSACTION` de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="37ffc-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="37ffc-112">Para obtener más información, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="37ffc-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="37ffc-113">Las transacciones que implican varios administradores de recursos, como un a transacción entre [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] y Oracle, requieren una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="37ffc-113">Transactions involving different resource managers, such as a transaction between [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37ffc-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="37ffc-114">In This Section</span></span>  
 [<span data-ttu-id="37ffc-115">Transacciones locales</span><span class="sxs-lookup"><span data-stu-id="37ffc-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="37ffc-116">Muestra cómo realizar transacciones en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="37ffc-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="37ffc-117">Transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="37ffc-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="37ffc-118">Describe cómo realizar transacciones distribuidas en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="37ffc-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="37ffc-119">Integración de System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="37ffc-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="37ffc-120">Describe la integración de <xref:System.Transactions> con [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] para trabajar con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="37ffc-120">Describes <xref:System.Transactions> integration with [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="37ffc-121">Simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="37ffc-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="37ffc-122">Describe la simultaneidad optimista y pesimista, y cómo puede probar las infracciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="37ffc-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ffc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="37ffc-123">See Also</span></span>  
 [<span data-ttu-id="37ffc-124">Principios de la transacción</span><span class="sxs-lookup"><span data-stu-id="37ffc-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [<span data-ttu-id="37ffc-125">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="37ffc-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="37ffc-126">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="37ffc-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="37ffc-127">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="37ffc-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="37ffc-128">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="37ffc-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="37ffc-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="37ffc-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
