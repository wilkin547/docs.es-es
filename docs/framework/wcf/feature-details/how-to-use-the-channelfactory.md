---
title: Procedimiento para usar ChannelFactory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 4bb2053fb50931756e79d5346a3f14d2acbe04f6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595315"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="4d3af-102">Procedimiento para usar ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="4d3af-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="4d3af-103">La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.</span><span class="sxs-lookup"><span data-stu-id="4d3af-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="4d3af-104">Crear y utilizar la clase ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="4d3af-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="4d3af-105">Compilar y ejecutar un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4d3af-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="4d3af-106">Para obtener más información, vea [diseñar e implementar servicios](../designing-and-implementing-services.md), [configurar servicios](../configuring-services.md)y [hospedar servicios](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d3af-106">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="4d3af-107">Use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato (interfaz) para el cliente.</span><span class="sxs-lookup"><span data-stu-id="4d3af-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="4d3af-108">En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.</span><span class="sxs-lookup"><span data-stu-id="4d3af-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d3af-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d3af-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
