---
title: "Recuperación de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: metadata [WCF], retrieving
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc96c585ba55fbf63283d7cb23fae5b364b0465
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-metadata"></a>Recuperación de metadatos
La recuperación de metadatos es el proceso de solicitar y recuperar los metadatos desde un punto de conexión de metadatos, como un punto de conexión de metadatos de WS-MetadataExchange (MEX) o de HTTP/GET.  
  
## <a name="retrieving-metadata-from-the-command-line-using-svcutilexe"></a>Recuperación de metadatos de la línea de comandos mediante Svcutil.exe  
 Puede recuperar metadatos del servicio mediante solicitudes HTTP/GET o WS-MetadataExchange mediante el uso de la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta y pasar la `/target:metadata` conmutador y una dirección. Svcutil.exe descarga los metadatos en la dirección especificada y guarda el archivo en el disco. Svcutil.exe utiliza una instancia <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> internamente y carga la configuración de extremo de <xref:System.ServiceModel.Description.IMetadataExchange> desde la configuración cuyo nombre coincide con el esquema de la dirección pasada a Svcutil.exe como entrada.  
  
## <a name="retrieving-metadata-programmatically-using-the-metadataexchangeclient"></a>Recuperación de metadatos mediante programación con MetadataExchangeClient  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puede recuperar metadatos de servicio mediante protocolos estandarizados como WS-MetadataExchange y solicitudes HTTP/GET. Ambos protocolos están admitidos por el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient>. Recupera metadatos de servicio utilizando el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> al proporcionar una dirección para el extremo de metadatos y un enlace opcional. El enlace utilizado por una instancia de <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> puede ser uno de los enlaces predeterminados de la clase estática <xref:System.ServiceModel.Description.MetadataExchangeBindings>, un enlace proporcionado por el usuario o un enlace cargado desde una configuración de extremo para el contrato `IMetadataExchange`. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> también puede resolver las referencias a la dirección URL HTTP a los metadatos utilizando el tipo <xref:System.Net.HttpWebRequest>.  
  
 De forma predeterminada, se ata una instancia <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> a una instancia <xref:System.ServiceModel.ChannelFactory> única. Puede cambiar o reemplazar la instancia <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> utilizada por <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> invalidando el método virtual <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. De igual forma, puede cambiar o reemplazar la instancia de <xref:System.Net.HttpWebRequest> utilizada por <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> para realizar solicitudes HTTP/GET mediante la invalidación del método virtual <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso de Svcutil.exe para descargar los documentos de metadatos](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Demuestra cómo usar Svcutil.exe para descargar los documentos de metadatos.  
  
 [Uso de MetadataResolver para obtener dinámicamente metadatos de enlace](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Muestra cómo utilizar <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> para obtener dinámicamente metadatos de enlace en el tiempo de ejecución.  
  
 [Uso de MetadataExchangeClient para recuperar metadatos](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> para descargar los archivos de metadatos en un objeto <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> que contiene objetos <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> para escribir en archivos o para otros usos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>
