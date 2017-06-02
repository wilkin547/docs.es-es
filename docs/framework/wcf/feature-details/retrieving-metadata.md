---
title: "Recuperaci&#243;n de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "metadatos [WCF], recuperación"
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Recuperaci&#243;n de metadatos
La recuperación de metadatos es el proceso de solicitar y recuperar los metadatos desde un extremo de metadatos, como un extremo de metadatos de WS\-MetadataExchange \(MEX\) o de HTTP\/GET.  
  
## Recuperación de metadatos de la línea de comandos mediante Svcutil.exe  
 Puede recuperar metadatos de servicio mediante solicitudes de WS\-MetadataExchange o HTTP\/GET utilizando la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) y pasando el modificador `/target:metadata` y una dirección.Svcutil.exe descarga los metadatos en la dirección especificada y guarda el archivo en el disco.Svcutil.exe utiliza una instancia <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> internamente y carga la configuración de extremo de <xref:System.ServiceModel.Description.IMetadataExchange> desde la configuración cuyo nombre coincide con el esquema de la dirección pasada a Svcutil.exe como entrada.  
  
## Recuperación de metadatos mediante programación con MetadataExchangeClient  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puede recuperar metadatos de servicio mediante protocolos estandarizados como WS\-MetadataExchange y solicitudes HTTP\/GET.Ambos protocolos están admitidos por el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient>.Recupera metadatos de servicio utilizando el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> al proporcionar una dirección para el extremo de metadatos y un enlace opcional.El enlace utilizado por una instancia de <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> puede ser uno de los enlaces predeterminados de la clase estática <xref:System.ServiceModel.Description.MetadataExchangeBindings>, un enlace proporcionado por el usuario o un enlace cargado desde una configuración de extremo para el contrato `IMetadataExchange`.<xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> también puede resolver las referencias a la dirección URL HTTP a los metadatos utilizando el tipo <xref:System.Net.HttpWebRequest>.  
  
 De forma predeterminada, se ata una instancia <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> a una instancia <xref:System.ServiceModel.ChannelFactory> única.Puede cambiar o reemplazar la instancia <xref:System.ServiceModel.ChannelFactory?displayProperty=fullName> utilizada por <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> invalidando el método virtual <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>.De igual forma, puede cambiar o reemplazar la instancia <xref:System.Net.HttpWebRequest> utilizada por <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> para realizar solicitudes HTTP\/GET invalidando el método virtual <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=fullName>.  
  
## En esta sección  
 [Cómo: Utilizar Svcutil.exe para descargar los documentos de metadatos](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Demuestra cómo usar Svcutil.exe para descargar los documentos de metadatos.  
  
 [Cómo: Utilizar MetadataResolver para obtener dinámicamente metadatos de enlace](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Muestra cómo utilizar <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName> para obtener dinámicamente metadatos de enlace en el tiempo de ejecución.  
  
 [Cómo: Utilizar MetadataExchangeClient para recuperar metadatos](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> para descargar los archivos de metadatos en un objeto <xref:System.ServiceModel.Description.MetadataSet?displayProperty=fullName> que contiene objetos <xref:System.ServiceModel.Description.MetadataSection?displayProperty=fullName> para escribir en archivos o para otros usos.  
  
## Vea también  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>