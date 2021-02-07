---
description: 'Más información acerca de: transacciones y simultaneidad'
title: Transacciones y simultaneidad
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: c77b9abc72ae662eec76fc40a9856ad73f000c27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766769"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="b1e0a-103">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="b1e0a-103">Transactions and Concurrency</span></span>

<span data-ttu-id="b1e0a-104">Una transacción consiste en un comando único o en un grupo de comandos que se ejecutan como un paquete.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-104">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="b1e0a-105">Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-105">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="b1e0a-106">Si en un punto de la transacción se produjera un error, todas las actualizaciones podrían revertirse y devolverse al estado que tenían antes de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-106">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="b1e0a-107">Una transacción debe ajustarse a las propiedades ACID (atomicidad, coherencia, aislamiento y durabilidad) para poder garantizar la coherencia de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-107">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="b1e0a-108">La mayoría de los sistemas de bases de datos relacionales, como Microsoft SQL Server, admiten transacciones, al proporcionar funciones de bloqueo, registro y administración de transacciones cada vez que una aplicación cliente realiza una operación de actualización, inserción o eliminación.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-108">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1e0a-109">Las transacciones que requieren varios recursos pueden reducir la simultaneidad si la duración del bloqueo es demasiado larga.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-109">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="b1e0a-110">Por ello, haga la transacción lo más corta posible.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-110">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="b1e0a-111">Las transacciones explícitas en procedimientos almacenados suelen dar mejores resultados cuando una transacción implica el uso de varias tablas en la misma base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-111">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="b1e0a-112">Se pueden crear transacciones en procedimientos almacenados de SQL Server mediante las instrucciones `BEGIN TRANSACTION`, `COMMIT TRANSACTION` o `ROLLBACK TRANSACTION` de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-112">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="b1e0a-113">Para obtener más información, vea Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-113">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="b1e0a-114">Para las transacciones que implican varios administradores de recursos, como una transacción entre SQL Server y Oracle, se necesita una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-114">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1e0a-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b1e0a-115">In This Section</span></span>  

 [<span data-ttu-id="b1e0a-116">Transacciones locales</span><span class="sxs-lookup"><span data-stu-id="b1e0a-116">Local Transactions</span></span>](local-transactions.md)  
 <span data-ttu-id="b1e0a-117">Muestra cómo realizar transacciones en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-117">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="b1e0a-118">Transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="b1e0a-118">Distributed Transactions</span></span>](distributed-transactions.md)  
 <span data-ttu-id="b1e0a-119">Describe cómo realizar transacciones distribuidas en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-119">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="b1e0a-120">Integración de System. Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1e0a-120">System.Transactions Integration with SQL Server</span></span>](system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="b1e0a-121">Se describe la integración de <xref:System.Transactions> con SQL Server para trabajar con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-121">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="b1e0a-122">Simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="b1e0a-122">Optimistic Concurrency</span></span>](optimistic-concurrency.md)  
 <span data-ttu-id="b1e0a-123">Describe la simultaneidad optimista y pesimista, y cómo puede probar las infracciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="b1e0a-123">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e0a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1e0a-124">See also</span></span>

- [<span data-ttu-id="b1e0a-125">Aspectos básicos de las transacciones</span><span class="sxs-lookup"><span data-stu-id="b1e0a-125">Transaction Fundamentals</span></span>](../transactions/transaction-fundamentals.md)
- [<span data-ttu-id="b1e0a-126">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="b1e0a-126">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="b1e0a-127">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="b1e0a-127">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="b1e0a-128">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="b1e0a-128">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="b1e0a-129">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="b1e0a-129">DbProviderFactories</span></span>](dbproviderfactories.md)
- [<span data-ttu-id="b1e0a-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b1e0a-130">ADO.NET Overview</span></span>](ado-net-overview.md)
