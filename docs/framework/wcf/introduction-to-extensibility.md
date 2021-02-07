---
description: 'Más información sobre: Introducción a la extensibilidad'
title: Introducción a la extensibilidad
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
ms.openlocfilehash: a3e614d107d2371076358f8e7786c1bb246e36eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732844"
---
# <a name="introduction-to-extensibility"></a>Introducción a la extensibilidad

El modelo de aplicación de Windows Communication Foundation (WCF) está diseñado para resolver la mayor parte de los requisitos de comunicación de cualquier aplicación distribuida. No obstante, siempre hay escenarios con los que el modelo de aplicación predeterminado y las implementaciones proporcionadas por sistema no son compatibles. El modelo de extensibilidad de WCF está diseñado para admitir escenarios personalizados, ya que permite modificar el comportamiento del sistema en todos los niveles, incluso en el punto en el que se reemplaza todo el modelo de aplicación. Este tema describe las distintas áreas de extensión e indica dónde obtener más información acerca de cada una de ellas.  
  
## <a name="areas-to-extend"></a>Áreas que pueden extenderse  

 Puede extenderse:  
  
- El tiempo de ejecución de la aplicación. De este modo se extiende la distribución y el procesamiento de mensajes para la aplicación. Esta área también incluye la extensión del sistema de seguridad, el sistema de metadatos, el sistema de serialización, y los enlaces y elementos de enlace que conectan la aplicación con el sistema del canal subyacente.  
  
- El canal y su tiempo de ejecución. Así se extiende el sistema que funciona en el nivel de mensaje, proporcionando compatibilidad con el protocolo, el transporte y la codificación.  
  
- El tiempo de ejecución del host. Se extiende la relación del dominio de aplicación de hospedaje al tiempo de ejecución del canal y de la aplicación.  
  
### <a name="extending-the-application-runtime"></a>Extender el tiempo de ejecución de la aplicación  

 En las aplicaciones WCF, existe una distinción entre los mensajes que están destinados a un canal correspondiente y los mensajes destinados a la propia aplicación. Los mensajes del canal admiten alguna funcionalidad relacionada con el canal, como establecer una conversación segura o una sesión de confianza. Estos mensajes no están disponibles para el tiempo de ejecución de la aplicación; se procesan antes de que se implique el nivel de la aplicación.  
  
 Los mensajes de la aplicación contienen datos destinados a un cliente u operación del servicio que usted o su cliente creó. Estos mensajes están disponibles para el sistema de extensión del nivel de la aplicación en forma de mensaje u objeto, dependiendo de sus necesidades.  
  
 Todos los mensajes atraviesan el sistema del canal; solo los mensajes de la aplicación se pasan desde el sistema del canal a la aplicación. Para crear una nueva funcionalidad en el nivel del canal, debe extender el sistema del canal. Para crear una nueva funcionalidad en el nivel de la aplicación, debe extender el tiempo de ejecución del servicio o del cliente (los distribuidores y generadores de canales, respectivamente). Para obtener más información acerca de cómo extender el tiempo de ejecución de la aplicación, consulte [extensión de ServiceHost y el nivel de modelo de servicio](./extending/extending-servicehost-and-the-service-model-layer.md).  
  
#### <a name="extending-security"></a>Extensión de la seguridad  

 Para crear mecanismos de seguridad personalizados, como tokens y credenciales, debe extender el sistema de seguridad. Para obtener más información, vea [ampliar la seguridad](./extending/extending-security.md).  
  
#### <a name="extending-metadata"></a>Extensión de metadatos  

 Para exponer sus metadatos de manera diferente a la predeterminada, es necesario extender el sistema de metadatos. Para obtener más información, vea [extender el sistema de metadatos](./extending/extending-the-metadata-system.md).  
  
#### <a name="extending-serialization"></a>Extender la serialización  

 Para crear los codificadores personalizados, proporcionar suplentes de datos u otro trabajo que implique la personalización de datos transferidos, es necesario extender el sistema de serialización. Para obtener más información, vea [extender codificadores y serializadores](./extending/extending-encoders-and-serializers.md).  
  
#### <a name="extending-bindings"></a>Extensión de enlaces  

 Para asociar canales de transporte o de protocolo con el nivel de aplicación, debe extender el sistema de enlace. Para obtener más información, vea [extender enlaces](./extending/extending-bindings.md).  
  
### <a name="extending-the-channel-system"></a>Extender el sistema del canal  

 Para crear canales que admitan los transportes personalizados o la funcionalidad del Protocolo, consulte [extensión de la capa de canales](./extending/extending-the-channel-layer.md).  
  
### <a name="extending-the-service-hosting-system"></a>Extensión del servicio de hospedaje del sistema  

 Para modificar el modelo de la aplicación de todo el servicio, es necesario extender la clase <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>. Para obtener más información, consulte [extensión de ServiceHost y la capa de modelo de servicio](./extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Para modificar la relación entre el dominio de aplicación de hospedaje y el host del servicio, es necesario extender la clase <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>. Para obtener más información, vea [extender el hospedaje mediante ServiceHostFactory](./extending/extending-hosting-using-servicehostfactory.md).  
  
## <a name="see-also"></a>Vea también

- [Extensión de WCF](./extending/index.md)
