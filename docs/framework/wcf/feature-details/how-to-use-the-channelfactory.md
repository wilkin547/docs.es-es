---
title: Procedimiento para usar ChannelFactory
description: Aprenda a crear un generador de canales para crear más de un canal para tener acceso a los servicios mediante un cliente WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7c87026ca4cf7c739f4615da9bc7f0272a382392
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246667"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="3c5ce-103">Procedimiento para usar ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="3c5ce-103">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="3c5ce-104">La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.</span><span class="sxs-lookup"><span data-stu-id="3c5ce-104">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="3c5ce-105">Crear y utilizar la clase ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="3c5ce-105">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="3c5ce-106">Compilar y ejecutar un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3c5ce-106">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="3c5ce-107">Para obtener más información, vea [diseñar e implementar servicios](../designing-and-implementing-services.md), [configurar servicios](../configuring-services.md)y [hospedar servicios](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3c5ce-107">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="3c5ce-108">Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato (interfaz) para el cliente.</span><span class="sxs-lookup"><span data-stu-id="3c5ce-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="3c5ce-109">En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.</span><span class="sxs-lookup"><span data-stu-id="3c5ce-109">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c5ce-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c5ce-110">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
