---
title: Procesar transacciones
description: Revise el procesamiento de transacciones en .NET. Las transacciones garantizan que los recursos orientados a datos no se actualicen permanentemente a menos que todas las operaciones se completen correctamente.
ms.date: 03/30/2017
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
ms.openlocfilehash: bbf2448128da7df8af415ff5dea7e3cd8af24d1e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186814"
---
# <a name="transaction-processing"></a><span data-ttu-id="87f2b-104">Procesamiento de transacciones</span><span class="sxs-lookup"><span data-stu-id="87f2b-104">Transaction Processing</span></span>

<span data-ttu-id="87f2b-105">Al comprar un libro desde una librería en línea, se intercambia dinero (en forma de crédito) por un libro.</span><span class="sxs-lookup"><span data-stu-id="87f2b-105">When you purchase a book from an online bookstore, you exchange money (in the form of credit) for a book.</span></span> <span data-ttu-id="87f2b-106">Si su crédito es bueno, una serie de operaciones relacionadas le aseguran que obtendrá el libro y que la librería obtendrá su dinero.</span><span class="sxs-lookup"><span data-stu-id="87f2b-106">If your credit is good, a series of related operations ensures that you get the book and the bookstore gets your money.</span></span> <span data-ttu-id="87f2b-107">Sin embargo, si se producir un error en una operación única en la serie durante el intercambio, todo el intercambio falla.</span><span class="sxs-lookup"><span data-stu-id="87f2b-107">However, if a single operation in the series fails during the exchange, the entire exchange fails.</span></span> <span data-ttu-id="87f2b-108">No obtiene el libro y la librería no obtiene su dinero.</span><span class="sxs-lookup"><span data-stu-id="87f2b-108">You do not get the book and the bookstore does not get your money.</span></span>  
  
 <span data-ttu-id="87f2b-109">La tecnología responsable para realizar el intercambio equilibrado y predecible se denomina procesamiento de transacciones.</span><span class="sxs-lookup"><span data-stu-id="87f2b-109">The technology responsible for making the exchange balanced and predictable is called transaction processing.</span></span> <span data-ttu-id="87f2b-110">Las transacciones le aseguran que los recursos orientados a datos no están actualizados permanentemente a menos que todas las operaciones dentro de la unidad transaccional se completen correctamente.</span><span class="sxs-lookup"><span data-stu-id="87f2b-110">Transactions ensure that data-oriented resources are not permanently updated unless all operations within the transactional unit complete successfully.</span></span> <span data-ttu-id="87f2b-111">Combinando un conjunto de operaciones relacionadas en una unidad que o tiene un éxito rotundo  o bien fracasa completamente, puede simplificar la recuperación de errores y realizar su aplicación con más confianza.</span><span class="sxs-lookup"><span data-stu-id="87f2b-111">By combining a set of related operations into a unit that either completely succeeds or completely fails, you can simplify error recovery and make your application more reliable.</span></span>  
  
 <span data-ttu-id="87f2b-112">Los sistemas del procesamiento de transacciones están compuestos de hardware del equipo y software que hospedan una aplicación orientada a transacciones que realiza las transacciones rutinarias necesarias para realizar el negocio.</span><span class="sxs-lookup"><span data-stu-id="87f2b-112">Transaction processing systems consist of computer hardware and software hosting a transaction-oriented application that performs the routine transactions necessary to conduct business.</span></span> <span data-ttu-id="87f2b-113">Los ejemplos incluyen sistemas que administran entradas del pedido de ventas, reservas de la línea aérea, nómina, registros del empleado, fabricación y envío.</span><span class="sxs-lookup"><span data-stu-id="87f2b-113">Examples include systems that manage sales order entry, airline reservations, payroll, employee records, manufacturing, and shipping.</span></span>  
  
 <span data-ttu-id="87f2b-114">En esta sección se proporciona tanto información general sobre procesamiento de transacciones como información concreta sobre cómo escribir las aplicaciones transaccionales y los administradores de recursos mediante Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87f2b-114">This section provides both general information on transaction processing, and specific information on how to write transactional applications and resource managers using the Microsoft .NET Framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87f2b-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="87f2b-115">In This Section</span></span>  

 [<span data-ttu-id="87f2b-116">Principios de la transacción</span><span class="sxs-lookup"><span data-stu-id="87f2b-116">Transaction Fundamentals</span></span>](transaction-fundamentals.md)  
 <span data-ttu-id="87f2b-117">Introduce condiciones del procesamiento de transacciones básicas y conceptos.</span><span class="sxs-lookup"><span data-stu-id="87f2b-117">Introduces basic transaction processing terms and concepts.</span></span>  
  
 [<span data-ttu-id="87f2b-118">Características proporcionadas por System.Transactions</span><span class="sxs-lookup"><span data-stu-id="87f2b-118">Features Provided by System.Transactions</span></span>](features-provided-by-system-transactions.md)  
 <span data-ttu-id="87f2b-119">Discute cómo puede utilizar las características en System.Transactions para escribir su propia aplicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="87f2b-119">Discusses how you can use features in System.Transactions to write your own transactional application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87f2b-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="87f2b-120">Reference</span></span>  

 <xref:System.Transactions>  
 <span data-ttu-id="87f2b-121">Proporciona las clases que permiten al código participar en transacciones.</span><span class="sxs-lookup"><span data-stu-id="87f2b-121">Provides classes that allow your code to participate in transactions.</span></span> <span data-ttu-id="87f2b-122">Las clases admiten transacciones con varios participantes distribuidos, varias notificaciones de fase e inscripciones duraderas.</span><span class="sxs-lookup"><span data-stu-id="87f2b-122">The classes support transactions with multiple distributed participants, multiple phase notifications, and durable enlistments.</span></span>
