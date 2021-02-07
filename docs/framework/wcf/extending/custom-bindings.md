---
description: 'Más información acerca de: enlaces personalizados'
title: Enlaces personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: ced0f9ada7238b43216a246d75dd391aa6eb3f2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735353"
---
# <a name="custom-bindings"></a>Enlaces personalizados

Puede usar la clase <xref:System.ServiceModel.Channels.CustomBinding> cuando uno de los enlaces proporcionados por el sistema no cumple los requisitos de su servicio. Todos los enlaces se construyen a partir de un conjunto ordenado de elementos de enlace. Los enlaces personalizados pueden crearse a partir de un conjunto de elementos de enlace proporcionado por el sistema o incluir elementos de enlace personalizado definidos por el usuario. Puede utilizar elementos de enlaces personalizados, por ejemplo, para habilitar el uso de nuevos transportes o codificadores en un extremo de servicio. Para obtener ejemplos prácticos, vea [ejemplos de enlace personalizado](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)). Para obtener más información, vea [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).

## <a name="construction-of-a-custom-binding"></a>Construcción de un enlace personalizado

Un enlace personalizado se construye utilizando el constructor <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:

- En la parte superior hay una clase <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.

- A continuación, hay una clase <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y mecanismos de ordenación, como se define en la especificación WS-ReliableMessaging. Una sesión puede cruzar SOAP y transportar intermediarios.

- A continuación, hay una clase <xref:System.ServiceModel.Channels.SecurityBindingElement> opcional que proporciona características de seguridad, como autorización, autenticación, protección y confidencialidad.

- A continuación, hay una clase <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> opcional que proporciona la capacidad de disponer de comunicación dúplex bidireccional con un protocolo de transporte que no admite la comunicación dúplex de forma nativa, como HTTP.

- A continuación, hay una clase <xref:System.ServiceModel.Channels.OneWayBindingElement>) opcional que proporciona comunicación unidireccional.

- A continuación, hay un elemento de enlace de seguridad de secuencia opcional que puede ser uno de los siguientes.

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- A continuación hay un elemento de enlace de codificación del mensaje requerido. Puede utilizar su propio codificador de mensajes o uno de los tres enlaces siguientes de codificación de mensajes:

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

En la parte inferior hay un elemento de transporte necesario. Puede utilizar su propio transporte o uno de los siguientes elementos de enlace de transporte Windows Communication Foundation (WCF) proporciona:

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

La tabla siguiente resume las opciones de cada nivel.

|Nivel|Opciones|Obligatorio|
|-----------|-------------|--------------|
|Transacciones|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|No|
|Confiabilidad|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|No|
|Seguridad|<xref:System.ServiceModel.Channels.SecurityBindingElement>|No|
|Encoding|Texto, binario, mecanismo de optimización de transmisión de mensajes (MTOM), personalizado|Sí|
|Transporte|TCP, HTTP, HTTPS, canalizaciones con nombre (también conocidas como IPC), igual a igual (P2P), Message Queuing (también conocido como MSMQ), personalizado|Sí|

Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.

## <a name="see-also"></a>Vea también

- [Información general acerca de la creación de puntos finales](../endpoint-creation-overview.md)
- [Utilización de enlaces para configurar servicios y clientes](../using-bindings-to-configure-services-and-clients.md)
- [Enlaces proporcionados por el sistema](../system-provided-bindings.md)
- [Procedimiento para personalizar un enlace proporcionado por el sistema](how-to-customize-a-system-provided-binding.md)
- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
- [Enlace personalizado](../samples/custom-binding.md)
