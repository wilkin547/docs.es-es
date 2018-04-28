---
title: Cómo utilizar ChannelFactory
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a076fb5b95c6750e6352235490b4e2e9ab883bbe
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="f799b-102">Cómo utilizar ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f799b-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="f799b-103">La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.</span><span class="sxs-lookup"><span data-stu-id="f799b-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="f799b-104">Crear y utilizar la clase ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f799b-104">To create and use the ChannelFactory class</span></span>  
  
1.  <span data-ttu-id="f799b-105">Compile y ejecute un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f799b-105">Build and run an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="f799b-106">Para obtener más información, consulte [diseñar e implementar servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md), [configurar Services](../../../../docs/framework/wcf/configuring-services.md), y [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f799b-106">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2.  <span data-ttu-id="f799b-107">Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato (interfaz) para el cliente.</span><span class="sxs-lookup"><span data-stu-id="f799b-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3.  <span data-ttu-id="f799b-108">En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.</span><span class="sxs-lookup"><span data-stu-id="f799b-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f799b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f799b-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
