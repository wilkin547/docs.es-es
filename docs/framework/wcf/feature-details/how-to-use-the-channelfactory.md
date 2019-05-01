---
title: Procedimiento para usar ChannelFactory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047261"
---
# <a name="how-to-use-the-channelfactory"></a>Procedimiento para usar ChannelFactory
La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Crear y utilizar la clase ChannelFactory  
  
1. Compilar y ejecutar un servicio de Windows Communication Foundation (WCF). Para obtener más información, consulte [diseño e implementación de servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md), [configurar Services](../../../../docs/framework/wcf/configuring-services.md), y [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
2. Use la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato (interfaz) para el cliente.  
  
3. En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
