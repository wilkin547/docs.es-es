---
title: Modelos de transacción
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499029"
---
# <a name="transaction-models"></a><span data-ttu-id="5c2c2-102">Modelos de transacción</span><span class="sxs-lookup"><span data-stu-id="5c2c2-102">Transaction Models</span></span>
<span data-ttu-id="5c2c2-103">En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="5c2c2-104">Cuando se usan transacciones en Windows Communication Foundation (WCF), es importante comprender que son no seleccionando entre modelos transaccionales diferentes, sino operando en diferentes capas de un modelo integrado y coherente.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="5c2c2-105">Las secciones siguientes describen los tres componentes de transacción primarios.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="5c2c2-106">Transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5c2c2-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="5c2c2-107">La compatibilidad con transacciones en WCF le permite que escribir servicios transaccionales.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="5c2c2-108">Además, con su compatibilidad para el protocolo de WS-AtomicTransaction (WS-AT), las aplicaciones pueden fluir transacciones a servicios Web creados con WCF o tecnología de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="5c2c2-109">En una aplicación o servicio WCF, características de la transacción de WCF proporcionan atributos y configuración para especificar de manera declarativa cómo y cuándo la infraestructura debe crear, fluir y sincronizar transacciones.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="5c2c2-110">Información general sobre las transacciones de System.Transactions</span><span class="sxs-lookup"><span data-stu-id="5c2c2-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="5c2c2-111">El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="5c2c2-112">Para obtener más información acerca de cómo crear una aplicación transaccional mediante estos dos modelos, vea [escribir una aplicación transaccional](http://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="5c2c2-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="5c2c2-113">En un servicio WCF o una aplicación, <xref:System.Transactions> proporciona el modelo de programación para crear las transacciones dentro de una aplicación de cliente y para interactuar explícitamente con una transacción, cuando se requiera, dentro de un servicio.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="5c2c2-114">Transacciones de MSDTC</span><span class="sxs-lookup"><span data-stu-id="5c2c2-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="5c2c2-115">Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="5c2c2-116">Para obtener más información, consulte el [referencia del programador de DTC](http://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="5c2c2-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="5c2c2-117">En una aplicación o servicio WCF, MSDTC proporciona la infraestructura para la coordinación de transacciones creada dentro de un cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="5c2c2-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
