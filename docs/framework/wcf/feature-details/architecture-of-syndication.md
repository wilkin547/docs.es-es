---
title: Arquitectura de distribución
ms.date: 03/30/2017
ms.assetid: ed4ca86e-e3d8-4acb-87aa-1921fbc353be
ms.openlocfilehash: bc8c9cfbdc4f5d8ee01dfcf5098cfbc74afc2467
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234809"
---
# <a name="architecture-of-syndication"></a>Arquitectura de distribución

La API de distribución está diseñada para proporcionar un modelo de programación neutral en cuanto al formato que permita escribir contenido distribuido en la conexión en una variedad de formatos. El modelo de datos abstracto está compuesto por las siguientes clases:  
  
- <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
- <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
- <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
- <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
- <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 Estas clases asignan estrechamente a las estructuras definidas en la especificación Atom 1.0, aunque algunos de los nombres son diferentes.  
  
 En Windows Communication Foundation (WCF), las fuentes de distribución se modelan como otro tipo de operación de servicio, una en la que el tipo de valor devuelto es una de las clases derivadas de <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> . La recuperación de una fuente se modela como un intercambio de mensajes de solicitud-respuesta. Un cliente envía una solicitud al servicio y el servicio responde. El mensaje de solicitud se establece a través de un protocolo de infraestructura (por ejemplo, HTTP sin formato) y el mensaje de respuesta contiene una carga útil que está compuesta por un formato de distribución reconocido (RSS 2.0 o Atom 1.0). Los servicios que implementan estos intercambios de mensajes se conocen como servicios de distribución.  
  
 El contrato para un servicio de distribución está compuesto por un conjunto de operaciones que devuelve una instancia de la clase <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. El siguiente ejemplo muestra una declaración de interfaz para un servicio de distribución.  
  
 [!code-csharp[S_UE_SyndicationBoth#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_syndicationboth/cs/service.cs#0)]  
  
 La compatibilidad con la distribución se basa en el modelo de programación REST de WCF que define el <xref:System.ServiceModel.WebHttpBinding> enlace, que se usa junto con <xref:System.ServiceModel.Description.WebHttpBehavior> para hacer que las fuentes estén disponibles como servicios. Para obtener más información sobre el modelo de programación REST de WCF, consulte [información general sobre el modelo de programación web http de WCF](wcf-web-http-programming-model-overview.md).  
  
> [!NOTE]
> La especificación Atom 1.0 permite especificar segundos fraccionarios en cualquiera de sus estructuras de fechas. Al serializar y deserializar la implementación de WCF, se omiten las fracciones de segundo.  
  
## <a name="object-model"></a>Modelo de objetos  

 El modelo de objetos para la distribución está compuesto de grupos de clases de las tablas siguientes.  
  
 Dar formato a las clases:  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter>|Una clase que serializa una instancia de <xref:System.ServiceModel.Syndication.SyndicationFeed> al formato Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601>|Una clase que serializa las clases derivadas de <xref:System.ServiceModel.Syndication.SyndicationFeed> al formato Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter>|Una clase que serializa una instancia de <xref:System.ServiceModel.Syndication.SyndicationItem> al formato Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601>|Una clase que serializa las clases derivadas de <xref:System.ServiceModel.Syndication.SyndicationItem> al formato Atom 1.0.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter>|Una clase que serializa una instancia de <xref:System.ServiceModel.Syndication.SyndicationFeed> al formato RSS 2.0.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>|Una clase que serializa las clases derivadas de <xref:System.ServiceModel.Syndication.SyndicationFeed> al formato RSS 2.0.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter>|Una clase que serializa una instancia de <xref:System.ServiceModel.Syndication.SyndicationItem> al formato RSS 2.0.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>|Una clase que serializa las clases derivadas de <xref:System.ServiceModel.Syndication.SyndicationItem> al formato RSS 2.0.|  
  
 Clases de modelo de objetos:  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.SyndicationCategory>|Una clase que representa la categoría de una fuente de distribución.|  
|<xref:System.ServiceModel.Syndication.SyndicationContent>|Una clase base que representa el contenido de distribución.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtension>|Una clase que representa una extensión de elemento de distribución.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection>|Una colección de objetos <xref:System.ServiceModel.Syndication.SyndicationElementExtension>.|  
|<xref:System.ServiceModel.Syndication.SyndicationFeed>|Una clase que representa un objeto de fuente de nivel superior.|  
|<xref:System.ServiceModel.Syndication.SyndicationItem>|Una clase que representa un elemento de fuente.|  
|<xref:System.ServiceModel.Syndication.SyndicationLink>|Una clase que representa un vínculo dentro de una fuente o elemento de distribución.|  
|<xref:System.ServiceModel.Syndication.SyndicationPerson>|Una clase que representa una estructura Atom Person.|  
|<xref:System.ServiceModel.Syndication.SyndicationVersions>|Una clase que representa las versiones del protocolo de distribución admitidas.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContent>|Una clase que representa cualquier contenido <xref:System.ServiceModel.Syndication.SyndicationItem> que se va a mostrar a un usuario final.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContentKind>|Una enumeración que representa los diferentes tipos de contenido de distribución de texto admitidos.|  
|<xref:System.ServiceModel.Syndication.UrlSyndicationContent>|Una clase que representa el contenido de distribución que consta de una dirección URL para otro recurso.|  
|<xref:System.ServiceModel.Syndication.XmlSyndicationContent>|Una clase que representa contenido de distribución que no se mostrará en un explorador.|  
  
 Las abstracciones de datos básicas en el modelo de objetos son Fuente y Elemento, que corresponde a las clases <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem>. Una Fuente expone algunos metadatos de nivel de fuente (por ejemplo, Título, Descripción y Autor), una ubicación para almacenar las extensiones desconocidas y un conjunto de elementos que constituyen el resto del contenido de la información de la fuente. Un Elemento permite que algunos metadatos de nivel de elemento (por ejemplo, Título, Resumen y PublicationDate) estén disponibles, una ubicación para almacenar las extensiones desconocidas y un elemento de contenido que contiene el resto del contenido de la información del elemento. Las abstracciones básicas de Fuente y Elemento son admitidas por clases adicionales que representan las estructuras de datos a las que se hace referencia en las especificaciones de Atom 1.0 y RSS.  
  
 La información llevada en una instancia de Fuente se puede convertir en una variedad de formatos XML. La clase <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> administra el proceso de convertir al formato XML y desde él. Esta clase es abstracta; se proporcionan implementaciones concretas para Atom 1.0 y RSS 2.0, <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> y <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>. Para utilizar las clases de Fuente derivadas, utilice <xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601> o <xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601> cuando le permitan especificar una clase Fuente derivada. Para utilizar las clases de elemento derivadas utilice <xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601> o <xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601> puesto que le permitan especificar una clase de elemento derivada. Los terceros pueden derivar su propia implementación de <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> para admitir los diferentes formatos de distribución.  
  
## <a name="extensibility"></a>Extensibilidad  
  
- Una característica clave de los protocolos de distribución es la extensibilidad. Atom 1.0 y RSS 2.0 le permiten agregar atributos y elementos a las fuentes de distribución que no están definidas en las especificaciones. El modelo de programación de distribución de WCF proporciona dos maneras de trabajar con atributos y extensiones personalizados: derivar una nueva clase y un acceso con tipo flexible. Para obtener más información, consulte [extensibilidad de distribución](syndication-extensibility.md).  
  
## <a name="see-also"></a>Vea también

- [Información general de distribución de WCF](wcf-syndication-overview.md)
- [Asignación del modelo de objetos de distribución de WCF a Atom y RSS](how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)
- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
