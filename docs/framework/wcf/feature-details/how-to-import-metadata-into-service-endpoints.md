---
title: Procedimiento para importar metadatos a puntos de conexión de servicio
ms.date: 03/30/2017
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
ms.openlocfilehash: 1de316b8e91739d5e3e24ff960e2cdfb33cc7fab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597064"
---
# <a name="how-to-import-metadata-into-service-endpoints"></a>Procedimiento para importar metadatos a puntos de conexión de servicio
En este tema se explica cómo importar metadatos en una colección de puntos de conexión de servicio y usar el servicio definido en el [Introducción](../samples/getting-started-sample.md). En este tema se muestra cómo crear una aplicación cliente que importa los metadatos desde el servicio y, a continuación, llama al método `Add` en el servicio.  
  
### <a name="to-import-metadata-into-service-endpoints"></a>Para importar metadatos a puntos de conexión de servicio  
  
1. Declare un objeto <xref:System.ServiceModel.EndpointAddress> e inicialícelo con el Identificador uniforme de recursos (URI) para la dirección del servicio de intercambio de metadatos (MEX).  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2. Cree <xref:System.ServiceModel.Description.MetadataExchangeClient>, pasando la dirección de MEX y llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>. Esto recupera los metadatos del servicio.  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3. Cree <xref:System.ServiceModel.Description.WsdlImporter>, pasando los metadatos previamente recuperados y llame <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>. Esto genera una colección de los objetos <xref:System.ServiceModel.Description.ContractDescription>. También podría llamar <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> o <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, dependiendo de sus necesidades.  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    > Después de haber importado los metadatos, no podrá crear un canal de cliente o exportar los metadatos. Esto es porque ninguna información de tipo está disponible en este punto. Se exige información de tipo para interactuar realmente con el servicio o exportar los metadatos. Para generar la información de tipo, necesita generar el código, tal como se muestra en los pasos 4 y 5. También podría utilizar la clase del asistente <xref:System.ServiceModel.Description.MetadataResolver>. Para obtener más información, vea [Cómo: usar MetadataResolver para obtener dinámicamente metadatos de enlace](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).  
  
4. Genere información de tipo para cada contrato.  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5. Ahora puede utilizar esta información. El ejemplo siguiente genera el código fuente C#:  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a>Vea también

- [Metadata](metadata.md)
- [Introducción](../samples/getting-started-sample.md)
