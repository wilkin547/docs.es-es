---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79970ad1220e3aab393a18cf52f94487702f37d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transactions"></a><span data-ttu-id="ffdce-102">Transacciones</span><span class="sxs-lookup"><span data-stu-id="ffdce-102">Transactions</span></span>
<span data-ttu-id="ffdce-103">Esta sección contiene ejemplos que muestran las transacciones de flujo de trabajo de [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffdce-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffdce-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ffdce-104">In This Section</span></span>  
 [<span data-ttu-id="ffdce-105">TransactionScope básico</span><span class="sxs-lookup"><span data-stu-id="ffdce-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="ffdce-106">Consta de cuatro escenarios que muestran cómo anidar instancias de <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="ffdce-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="ffdce-107">Uso de TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="ffdce-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="ffdce-108">Muestra cómo pasar una transacción de un cliente a un servidor utilizando <xref:System.Activities.Statements.TransactionScope> para crear una transacción en el cliente y <xref:System.ServiceModel.Activities.TransactedReceiveScope> para recibir un mensaje con una transacción de flujo y determinar la duración de la transacción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ffdce-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="ffdce-109">Anidamiento de TransactionScope dentro de un servicio</span><span class="sxs-lookup"><span data-stu-id="ffdce-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="ffdce-110">Consta de dos escenarios que muestran cómo administrar las instancias de la actividad <xref:System.Activities.Statements.TransactionScope> dentro de un servicio.</span><span class="sxs-lookup"><span data-stu-id="ffdce-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
