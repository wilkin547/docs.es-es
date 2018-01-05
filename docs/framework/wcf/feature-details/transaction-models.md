---
title: "Modelos de transacción"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 782a6b5bdb206d285d619b8085993b591785aca5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-models"></a><span data-ttu-id="7ee84-102">Modelos de transacción</span><span class="sxs-lookup"><span data-stu-id="7ee84-102">Transaction Models</span></span>
<span data-ttu-id="7ee84-103">En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.</span><span class="sxs-lookup"><span data-stu-id="7ee84-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="7ee84-104">Al utilizar las transacciones en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], es importante entender que no está seleccionando entre modelos transaccionales diferentes, sino operando en diferentes capas de un modelo integrado y coherente.</span><span class="sxs-lookup"><span data-stu-id="7ee84-104">When using transactions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="7ee84-105">Las secciones siguientes describen los tres componentes de transacción primarios.</span><span class="sxs-lookup"><span data-stu-id="7ee84-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="7ee84-106">Transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7ee84-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="7ee84-107">La compatibilidad con transacciones en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le permite escribir servicios transaccionales.</span><span class="sxs-lookup"><span data-stu-id="7ee84-107">The transaction support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you write transactional services.</span></span> <span data-ttu-id="7ee84-108">Además, con su compatibilidad para el protocolo WS-AtomicTransaction (WS-AT), las aplicaciones pueden hacer fluir transacciones a los servicios web creados mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o tecnologías de otros fabricantes.</span><span class="sxs-lookup"><span data-stu-id="7ee84-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or third-party technology.</span></span>  
  
 <span data-ttu-id="7ee84-109">En un servicio o aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las características de transacciones de  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporcionan atributos y configuración para especificar de manera declarativa cómo y cuándo la infraestructura debería crearse, fluir y sincronizar transacciones.</span><span class="sxs-lookup"><span data-stu-id="7ee84-109">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="7ee84-110">Información general sobre las transacciones de System.Transactions</span><span class="sxs-lookup"><span data-stu-id="7ee84-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="7ee84-111">El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.</span><span class="sxs-lookup"><span data-stu-id="7ee84-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7ee84-112">cómo crear una aplicación transaccional mediante estos dos modelos, vea [escribir una aplicación transaccional](http://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="7ee84-112"> how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="7ee84-113">En un servicio o aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.Transactions> proporciona el modelo de programación para crear las transacciones dentro de una aplicación cliente y para interactuar explícitamente con una transacción, cuando se requiera, dentro de un servicio.</span><span class="sxs-lookup"><span data-stu-id="7ee84-113">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="7ee84-114">Transacciones de MSDTC</span><span class="sxs-lookup"><span data-stu-id="7ee84-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="7ee84-115">Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="7ee84-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7ee84-116">el [referencia del programador de DTC](http://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="7ee84-116"> the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="7ee84-117">En un servicio o aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], MSDTC proporciona la infraestructura para la coordinación de transacciones creada dentro de un cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="7ee84-117">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
