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
# <a name="how-to-use-the-channelfactory"></a>Procedimiento para usar ChannelFactory
La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Crear y utilizar la clase ChannelFactory  
  
1. Compilar y ejecutar un servicio de Windows Communication Foundation (WCF). Para obtener más información, vea [diseñar e implementar servicios](../designing-and-implementing-services.md), [configurar servicios](../configuring-services.md)y [hospedar servicios](../hosting-services.md).  
  
2. Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato (interfaz) para el cliente.  
  
3. En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
