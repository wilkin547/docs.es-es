---
title: "Utilización de WS-AtomicTransaction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 124c5dc0f6db94ae459fe140bd7a4290aa56e04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="f734b-102">Utilización de WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="f734b-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="f734b-103">WS-AtomicTransaction (WS-AT) es un protocolo de transacción interoperable.</span><span class="sxs-lookup"><span data-stu-id="f734b-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="f734b-104">Permite fluir las transacciones distribuidas utilizando los mensajes de servicio web y coordinar de una manera interoperable entre las infraestructuras de transacción heterogéneas.</span><span class="sxs-lookup"><span data-stu-id="f734b-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="f734b-105">WS-AT utiliza el protocolo de confirmación en dos fases para controlar un resultado atómico entre las aplicaciones distribuidas, administradores de transacciones y administradores de recursos.</span><span class="sxs-lookup"><span data-stu-id="f734b-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="f734b-106">La implementación de WS-AT que [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona incluye un servicio de protocolo integrado en el administrador de transacciones de Microsoft DTC (Coordinador de transacciones distribuidas, MSDTC).</span><span class="sxs-lookup"><span data-stu-id="f734b-106">The WS-AT implementation [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="f734b-107">Con WS-AT, las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden fluir transacciones a otras aplicaciones, incluidos los servicios web creados con tecnología de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="f734b-107">Using WS-AT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="f734b-108">Al fluir una transacción entre una aplicación cliente y una aplicación de servidor, el protocolo de transacción utilizado está determinado por el enlace que el servidor expone en el punto de conexión del cliente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f734b-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="f734b-109">Algunos enlaces proporcionados por el sistema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] especifican el protocolo `OleTransactions` como formato de propagación de transacción de manera predeterminada, mientras otros especifican WS-AT.</span><span class="sxs-lookup"><span data-stu-id="f734b-109">Some [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="f734b-110">También puede modificar mediante programación la opción de protocolo de transacción dentro de un enlace determinado.</span><span class="sxs-lookup"><span data-stu-id="f734b-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="f734b-111">La opción del protocolo influye en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f734b-111">The choice of protocol influences:</span></span>  
  
-   <span data-ttu-id="f734b-112">El formato de los encabezados del mensaje utilizado para fluir la transacción desde el cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="f734b-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
-   <span data-ttu-id="f734b-113">El protocolo de red utilizado para ejecutar el protocolo de confirmación en dos fases entre el administrador de transacciones del cliente y la transacción del servidor para resolver el resultado de la transacción.</span><span class="sxs-lookup"><span data-stu-id="f734b-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="f734b-114">Si el servidor y el cliente se escriben utilizando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], no necesita utilizar WS-AT.</span><span class="sxs-lookup"><span data-stu-id="f734b-114">If the server and client are written using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you do not need to use WS-AT.</span></span> <span data-ttu-id="f734b-115">En su lugar, puede utilizar la configuración predeterminada de `NetTcpBinding` con el atributo `TransactionFlow` habilitado, que utilizará en su lugar el protocolo `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="f734b-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f734b-116">[ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f734b-116"> [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="f734b-117">De lo contrario, si está fluyendo las transacciones a los servicios web creados con tecnologías de otro fabricante, deberá utilizar WS-AT.</span><span class="sxs-lookup"><span data-stu-id="f734b-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f734b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f734b-118">See Also</span></span>  
 [<span data-ttu-id="f734b-119">Configuración de la compatibilidad con WS-Atomic Transaction</span><span class="sxs-lookup"><span data-stu-id="f734b-119">Configuring WS-Atomic Transaction Support</span></span>](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
