---
title: Procesar transacciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a6dcd11d34f0b81d6d3982ef1c6ab211d94818b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-processing"></a><span data-ttu-id="60071-102">Procesar transacciones</span><span class="sxs-lookup"><span data-stu-id="60071-102">Transaction Processing</span></span>
<span data-ttu-id="60071-103">Al comprar un libro desde una librería en línea, se intercambia dinero (en forma de crédito) por un libro.</span><span class="sxs-lookup"><span data-stu-id="60071-103">When you purchase a book from an online bookstore, you exchange money (in the form of credit) for a book.</span></span> <span data-ttu-id="60071-104">Si su crédito es bueno, una serie de operaciones relacionadas le aseguran que obtendrá el libro y que la librería obtendrá su dinero.</span><span class="sxs-lookup"><span data-stu-id="60071-104">If your credit is good, a series of related operations ensures that you get the book and the bookstore gets your money.</span></span> <span data-ttu-id="60071-105">Sin embargo, si se producir un error en una operación única en la serie durante el intercambio, todo el intercambio falla.</span><span class="sxs-lookup"><span data-stu-id="60071-105">However, if a single operation in the series fails during the exchange, the entire exchange fails.</span></span> <span data-ttu-id="60071-106">No obtiene el libro y la librería no obtiene su dinero.</span><span class="sxs-lookup"><span data-stu-id="60071-106">You do not get the book and the bookstore does not get your money.</span></span>  
  
 <span data-ttu-id="60071-107">La tecnología responsable para realizar el intercambio equilibrado y predecible se denomina procesamiento de transacciones.</span><span class="sxs-lookup"><span data-stu-id="60071-107">The technology responsible for making the exchange balanced and predictable is called transaction processing.</span></span> <span data-ttu-id="60071-108">Las transacciones le aseguran que los recursos orientados a datos no están actualizados permanentemente a menos que todas las operaciones dentro de la unidad transaccional se completen correctamente.</span><span class="sxs-lookup"><span data-stu-id="60071-108">Transactions ensure that data-oriented resources are not permanently updated unless all operations within the transactional unit complete successfully.</span></span> <span data-ttu-id="60071-109">Combinando un conjunto de operaciones relacionadas en una unidad que o tiene un éxito rotundo  o bien fracasa completamente, puede simplificar la recuperación de errores y realizar su aplicación con más confianza.</span><span class="sxs-lookup"><span data-stu-id="60071-109">By combining a set of related operations into a unit that either completely succeeds or completely fails, you can simplify error recovery and make your application more reliable.</span></span>  
  
 <span data-ttu-id="60071-110">Los sistemas del procesamiento de transacciones están compuestos de hardware del equipo y software que hospedan una aplicación orientada a transacciones que realiza las transacciones rutinarias necesarias para realizar el negocio.</span><span class="sxs-lookup"><span data-stu-id="60071-110">Transaction processing systems consist of computer hardware and software hosting a transaction-oriented application that performs the routine transactions necessary to conduct business.</span></span> <span data-ttu-id="60071-111">Los ejemplos incluyen sistemas que administran entradas del pedido de ventas, reservas de la línea aérea, nómina, registros del empleado, fabricación y envío.</span><span class="sxs-lookup"><span data-stu-id="60071-111">Examples include systems that manage sales order entry, airline reservations, payroll, employee records, manufacturing, and shipping.</span></span>  
  
 <span data-ttu-id="60071-112">En esta sección se proporciona tanto información general sobre procesamiento de transacciones como información concreta sobre cómo escribir las aplicaciones transaccionales y los administradores de recursos mediante Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60071-112">This section provides both general information on transaction processing, and specific information on how to write transactional applications and resource managers using the Microsoft .NET Framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60071-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="60071-113">In This Section</span></span>  
 [<span data-ttu-id="60071-114">Principios de la transacción</span><span class="sxs-lookup"><span data-stu-id="60071-114">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 <span data-ttu-id="60071-115">Introduce condiciones del procesamiento de transacciones básicas y conceptos.</span><span class="sxs-lookup"><span data-stu-id="60071-115">Introduces basic transaction processing terms and concepts.</span></span>  
  
 [<span data-ttu-id="60071-116">Características proporcionadas por System.Transactions</span><span class="sxs-lookup"><span data-stu-id="60071-116">Features Provided by System.Transactions</span></span>](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)  
 <span data-ttu-id="60071-117">Discute cómo puede utilizar las características en System.Transactions para escribir su propia aplicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="60071-117">Discusses how you can use features in System.Transactions to write your own transactional application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="60071-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="60071-118">Reference</span></span>  
 <xref:System.Transactions>  
 <span data-ttu-id="60071-119">Proporciona las clases que permiten al código participar en transacciones.</span><span class="sxs-lookup"><span data-stu-id="60071-119">Provides classes that allow your code to participate in transactions.</span></span> <span data-ttu-id="60071-120">Las clases admiten transacciones con varios participantes distribuidos, varias notificaciones de fase e inscripciones duraderas.</span><span class="sxs-lookup"><span data-stu-id="60071-120">The classes support transactions with multiple distributed participants, multiple phase notifications, and durable enlistments.</span></span>
