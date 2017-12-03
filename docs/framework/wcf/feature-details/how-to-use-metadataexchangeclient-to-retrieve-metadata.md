---
title: "Cómo: Utilizar MetadataExchangeClient para recuperar metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0754e9dc-13c5-45c2-81b5-f3da466e5a87
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cccbf343acc74b3e0da0f55e497f19ca15e27892
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-metadataexchangeclient-to-retrieve-metadata"></a>Cómo: Utilizar MetadataExchangeClient para recuperar metadatos
Utilice la clase <xref:System.ServiceModel.Description.MetadataExchangeClient> para descargar metadatos mediante el protocolo WS-MetadataExchange (MEX). Los archivos de metadatos recuperados se devuelven como un objeto <xref:System.ServiceModel.Description.MetadataSet>. El objeto <xref:System.ServiceModel.Description.MetadataSet> devuelto contiene una colección de objetos <xref:System.ServiceModel.Description.MetadataSection>, cada uno de los cuales contiene un dialecto de metadatos concreto y un identificador. Puede escribir los metadatos devueltos en los archivos o, si éstos contienen los documentos del Lenguaje de descripción de servicios Web (WSDL), podrá importar los metadatos mediante <xref:System.ServiceModel.Description.WsdlImporter>.  
  
 Los constructores <xref:System.ServiceModel.Description.MetadataExchangeClient> que toman una dirección utilizan el enlace en la clase estática <xref:System.ServiceModel.Description.MetadataExchangeBindings> que coincide con el esquema del Identificador uniforme de recursos (URI) de la dirección. Puede utilizar alternativamente el constructor <xref:System.ServiceModel.Description.MetadataExchangeClient> que le permite especificar explícitamente el enlace que vaya a utilizar. El enlace especificado se utiliza para resolver todas las referencias de los metadatos.  
  
 Al igual que cualquier otro cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient> proporciona un constructor para cargar configuraciones de extremo de cliente mediante el nombre de configuración del extremo. La configuración del extremo especificada debe especificar el contrato <xref:System.ServiceModel.Description.IMetadataExchange>. No se carga la dirección en la configuración del extremo, por lo que debe utilizar una de las sobrecargas <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> que toman una dirección. Cuando se especifica la dirección de los metadatos que utilizan una instancia <xref:System.ServiceModel.EndpointAddress>, el <xref:System.ServiceModel.Description.MetadataExchangeClient> asume que la dirección señala a un extremo MEX. Si especifica la dirección de los metadatos como una dirección URL, a continuación, también necesita especificar qué <xref:System.ServiceModel.Description.MetadataExchangeClientMode> utilizar, MEX o HTTP GET.  
  
> [!IMPORTANT]
>  De forma predeterminada, <xref:System.ServiceModel.Description.MetadataExchangeClient> resuelve todas las referencias para el usuario, incluidas las importaciones e inclusiones de esquema WSDL y XML. Puede deshabilitar esta funcionalidad definiendo la propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> en `false`. Puede controlar el número máximo de referencias que resolver utilizando la propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>. Puede utilizar esta propiedad junto con la propiedad `MaxReceivedMessageSize` en el enlace para controlar cuántos metadatos se recuperan.  
  
### <a name="to-use-metadataexchangeclient-to-obtain-metadata"></a>Para utilizar MetadataExchangeClient para obtener metadatos  
  
1.  Cree un nuevo objeto <xref:System.ServiceModel.Description.MetadataExchangeClient> especificando explícitamente un enlace, un nombre de configuración de extremo o la dirección de los metadatos.  
  
2.  Configure <xref:System.ServiceModel.Description.MetadataExchangeClient> para ajustarlo a sus necesidades. Por ejemplo, puede especificar las credenciales que se van a usar cuando se solicitan metadatos, controlar cómo se resuelven las referencias a metadatos y definir la propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A> para controlar cuánto tiempo tiene la solicitud de los metadatos para volver antes de caducar.  
  
3.  Obtenga el objeto <xref:System.ServiceModel.Description.MetadataSet> que contiene los metadatos recuperados llamando a uno de los métodos <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>. Observe que solo puede utilizar la sobrecarga <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> que no toma ningún argumento si especificó explícitamente una dirección al construir <xref:System.ServiceModel.Description.MetadataExchangeClient>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo utilizar <xref:System.ServiceModel.Description.MetadataExchangeClient> para descargar y enumerar los archivos de metadatos.  

 [!code-csharp[MetadataResolver#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/metadataresolver/cs/client.cs#3)]  

## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar este ejemplo de código, debe hacer referencia al ensamblado System.ServiceModel.dll e importar el espacio de nombres <xref:System.ServiceModel.Description>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.MetadataResolver>  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>  
 <xref:System.ServiceModel.Description.WsdlImporter>
