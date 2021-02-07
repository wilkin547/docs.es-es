---
description: 'Más información acerca de: modelos de transacción'
title: Modelos de transacción
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9abccf74ef5b242cfbe63605046e30e397b8eda6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752709"
---
# <a name="transaction-models"></a><span data-ttu-id="26359-103">Modelos de transacción</span><span class="sxs-lookup"><span data-stu-id="26359-103">Transaction Models</span></span>

<span data-ttu-id="26359-104">En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.</span><span class="sxs-lookup"><span data-stu-id="26359-104">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="26359-105">Al utilizar transacciones en Windows Communication Foundation (WCF), es importante entender que no está seleccionando entre diferentes modelos transaccionales, sino que funciona en diferentes capas de un modelo integrado y coherente.</span><span class="sxs-lookup"><span data-stu-id="26359-105">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="26359-106">Las secciones siguientes describen los tres componentes de transacción primarios.</span><span class="sxs-lookup"><span data-stu-id="26359-106">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="26359-107">Transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="26359-107">Windows Communication Foundation Transactions</span></span>  

 <span data-ttu-id="26359-108">La compatibilidad con transacciones en WCF permite escribir servicios transaccionales.</span><span class="sxs-lookup"><span data-stu-id="26359-108">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="26359-109">Además, gracias a la compatibilidad con el protocolo WS-AtomicTransaction (WS-AT), las aplicaciones pueden fluir transacciones a servicios web creados mediante WCF o tecnología de terceros.</span><span class="sxs-lookup"><span data-stu-id="26359-109">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="26359-110">En una aplicación o servicio WCF, las características de transacción WCF proporcionan atributos y configuraciones para especificar mediante declaración cómo y cuándo la infraestructura debe crear, fluir y sincronizar transacciones.</span><span class="sxs-lookup"><span data-stu-id="26359-110">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="26359-111">Información general sobre las transacciones de System.Transactions</span><span class="sxs-lookup"><span data-stu-id="26359-111">System.Transactions Transactions</span></span>  

 <span data-ttu-id="26359-112">El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.</span><span class="sxs-lookup"><span data-stu-id="26359-112">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="26359-113">Para obtener más información sobre cómo crear una aplicación transaccional con estos dos modelos, vea [escribir una aplicación transaccional](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="26359-113">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="26359-114">En una aplicación o servicio WCF, <xref:System.Transactions> proporciona el modelo de programación para crear transacciones en una aplicación cliente y para interactuar explícitamente con una transacción, cuando es necesario, dentro de un servicio.</span><span class="sxs-lookup"><span data-stu-id="26359-114">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="26359-115">Transacciones de MSDTC</span><span class="sxs-lookup"><span data-stu-id="26359-115">MSDTC Transactions</span></span>  

 <span data-ttu-id="26359-116">Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="26359-116">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="26359-117">Para obtener más información, vea la [Referencia del programador de DTC](/previous-versions/windows/desktop/ms686108(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="26359-117">For more information, see the [DTC Programmer's Reference](/previous-versions/windows/desktop/ms686108(v=vs.85)).</span></span>  
  
 <span data-ttu-id="26359-118">En una aplicación o servicio WCF, MSDTC proporciona la infraestructura para la coordinación de transacciones creadas dentro de un cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="26359-118">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
