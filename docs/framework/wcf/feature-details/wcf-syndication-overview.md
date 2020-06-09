---
title: Información general de distribución de WCF
ms.date: 03/30/2017
ms.assetid: af6d4c39-e5e8-4099-aee6-5261feff9107
ms.openlocfilehash: 4f72a6d797f195108401a361cc73d74d309d5602
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600963"
---
# <a name="wcf-syndication-overview"></a>Información general de distribución de WCF
Windows Communication Foundation (WCF) proporciona compatibilidad para exponer las fuentes de distribución desde un servicio WCF. La distribución es un mecanismo de integración de aplicaciones en el que un servidor expone algunos datos de la aplicación en un formato interoperable conocido como fuente. Una fuente es una colección de datos de la aplicación que está compuesta de algunos metadatos de fuente (título, autor, dirección URL y otros metadatos) y una serie de elementos de fuente. Dentro de la fuente, los elementos de fuente están ordenados normalmente en orden cronológico inverso. Un elemento de fuente está compuesto por un conjunto estándar de metadatos de elementos (título, dirección URL, fecha de creación, categoría y otros metadatos de elementos) y una cantidad arbitraria de datos específicos de la aplicación. Los dos tipos más comunes de fuentes de distribución son Really Simple Syndication (RSS) 2,0 y Atom 1,0, que son compatibles con WCF.  
  
## <a name="object-model"></a>Modelo de objetos  
 WCF define un conjunto de clases específicas de distribución que permiten trabajar con fuentes, elementos de fuente y los metadatos relacionados de una manera independiente del formato: <xref:System.ServiceModel.Syndication.SyndicationFeed> , <xref:System.ServiceModel.Syndication.SyndicationItem> , <xref:System.ServiceModel.Syndication.SyndicationPerson> , <xref:System.ServiceModel.Syndication.SyndicationLink> y otras clases específicas de la distribución. WCF también define las clases de infraestructura que se basan en el modelo de programación REST de WCF para proporcionar compatibilidad con la distribución, incluidas: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> y <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> . Las clases de formateador de fuente permiten serializar el modelo de objetos a y desde RSS 2.0 y Atom 1.0.  
  
## <a name="scenarios"></a>Escenarios  
 Un uso común actual de distribución es el blogging, donde el autor del blog publica periódicamente algún tipo de información. Ésta puede ser texto, imágenes, audio u otros tipos de información. Muchos periódicos y revistas también publican artículos o noticias mediante distribución. Al suscribirse a este tipo de fuentes, un usuario puede mantenerse al día con toda la nueva información procedente de estos sitios. Aunque la distribución está asociada comúnmente a blogs y editores, se puede utilizar con cualquier aplicación que exponga una colección de información, como, por ejemplo, una base de datos de errores que desea exponer mediante una fuente de distribución. Puede crear un servicio WCF que exponga una operación denominada `CodeDefects` . Esta operación podría tomar un parámetro que especifique la dirección de correo electrónico de la persona que tiene los errores que desea recuperar. Un cliente puede utilizar la siguiente dirección URL para llamar a la operación: `http://someserver/bugDatabase/CodeDefects?user=johndoe` .  
  
## <a name="syndication-formats"></a>Formatos de distribución   
 La plataforma de sindicación de WCF es compatible con RSS 2,0 y Atom 1,0.  
  
## <a name="see-also"></a>Vea también

- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
