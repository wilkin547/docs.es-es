---
title: Utilización de enlaces para configurar servicios y clientes
description: Los enlaces contienen información de configuración utilizada por los clientes o servicios WFC. Obtenga información sobre cómo definir enlaces y cómo especificar un enlace para un punto de conexión de servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
ms.openlocfilehash: 38fa4a928c74f9fff7b67f2479f9304331361fef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289885"
---
# <a name="using-bindings-to-configure-services-and-clients"></a>Utilización de enlaces para configurar servicios y clientes

Los enlaces son los objetos que especifican los datos de comunicación exigidos para conectar a un punto de conexión. Más específicamente, los enlaces contienen información de configuración utilizada para crear el cliente o servicio en tiempo de ejecución mediante la definición de las características de transportes, formatos de la conexión (codificación de mensajes) y protocolos que se utilizarán en el punto de conexión respectivo o canal de cliente. Para crear un servicio de Windows Communication Foundation (WCF) en funcionamiento, cada punto de conexión del servicio requiere un enlace. Este tema explica qué enlaces son, cómo se definen, y cómo se especifica un enlace determinado para un punto de conexión.  
  
## <a name="what-a-binding-defines"></a>Qué define un enlace  

 La información de un enlace puede ser muy básica o muy compleja. El enlace más básico especifica solo el protocolo de transporte (como HTTP) que se debe utilizar para conectar al extremo. Más generalmente, la información que contiene un enlace sobre cómo conectarse a un extremo queda incluida en una de las categorías de la tabla siguiente.  
  
 Protocolos  
 Determina el mecanismo de seguridad utilizado, función de la mensajería de confianza o configuración de flujo de contexto de transacción.  
  
 Transporte  
 Determina el protocolo de transporte subyacente que se utilizará (por ejemplo, TCP o HTTP).  
  
 Encoding  
 Determina la codificación del mensaje, por ejemplo, texto/XML, binario o Mecanismo de optimización de transmisión del mensaje (MTOM), que determinan cómo se representan los mensajes como secuencias de bytes en la conexión.  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  

 WCF incluye un conjunto de enlaces proporcionados por el sistema que están diseñados para cubrir la mayoría de los requisitos y escenarios de la aplicación. Las clases siguientes representan algunos ejemplos de enlaces proporcionados por el sistema:  
  
- <xref:System.ServiceModel.BasicHttpBinding>: Un enlace de protocolo HTTP conveniente para conectar a los Servicios Web que cumple a la especificación del WS-I Basic Profile 1.1 (por ejemplo, servicios web ASP.NET [ASMX] - servicios basados).  
  
- <xref:System.ServiceModel.WSHttpBinding>: Un enlace de protocolo HTTP conveniente para conectar a los extremos que cumplen con los protocolos de especificaciones de servicios Web.  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>: Utiliza la codificación binaria de .NET y las tecnologías de tramas junto con el transporte de canalización con nombre de Windows para conectarse a otros puntos de conexión de WCF en el mismo equipo.  
  
- <xref:System.ServiceModel.NetMsmqBinding>: Utiliza la codificación binaria de .NET y las tecnologías de tramas junto con Message Queue Server (también conocido como MSMQ) para crear conexiones de mensajes en cola con otros extremos de WCF.  
  
 Para obtener una lista completa de los enlaces proporcionados por el sistema, con descripciones, vea [enlaces proporcionados por el sistema](system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Enlaces personalizados  

 Si la colección de enlaces proporcionada por el sistema no tiene la combinación correcta de características que necesita una aplicación de servicio, puede crear un enlace <xref:System.ServiceModel.Channels.CustomBinding>. Para obtener más información sobre los elementos de un <xref:System.ServiceModel.Channels.CustomBinding> enlace, vea [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) y [enlaces personalizados](./extending/custom-bindings.md).  
  
## <a name="using-bindings"></a>Utilizar los enlaces  

 El uso de enlaces conlleva dos pasos básicos:  
  
1. Seleccione o defina un enlace. El método más fácil es elegir uno de los enlaces proporcionados por el sistema y utilizar su configuración predeterminada. Puede elegir también un enlace proporcionado por el sistema y restablecer sus valores de propiedad para satisfacer sus necesidades También puede crear un enlace personalizado y establecer las propiedades como necesite.  
  
2. Cree un punto de conexión que utiliza este enlace.  
  
## <a name="code-and-configuration"></a>Código y configuración  

 Puede definir o configurar los enlaces a través del código o configuración. Estos dos enfoques son independientes según el tipo de enlace utilizado, por ejemplo, si utiliza un enlace proporcionado por el sistema o un enlace <xref:System.ServiceModel.Channels.CustomBinding>. En general, el uso de código proporciona un control total sobre la definición de un enlace cuando se compila. Por otro lado, el uso de la configuración permite a un administrador del sistema o al usuario de un servicio o cliente WCF cambiar los parámetros de los enlaces. Esta flexibilidad es a menudo deseable porque no hay ninguna manera de predecir los requisitos de máquina y las condiciones de red específicos en los que se va a implementar una aplicación WCF. Separar la información de enlace (y direccionamiento) del código permite a los administradores cambiar los datos obligatorios sin tener que recompilar o implementar de nuevo la aplicación. Tenga en cuenta que si el enlace se define en código, sobrescribe las definiciones basadas en configuración realizadas en el archivo de configuración. Para obtener ejemplos de estos enfoques, consulte los temas siguientes:  
  
- [Cómo: hospedar un servicio WCF en una aplicación administrada](how-to-host-a-wcf-service-in-a-managed-application.md) proporciona un ejemplo de cómo crear un enlace en el código.  
  
- [Tutorial: crear un cliente de Windows Communication Foundation](how-to-create-a-wcf-client.md) proporciona un ejemplo de creación de un cliente mediante la configuración.  
  
## <a name="see-also"></a>Vea también

- [Información general acerca de la creación de puntos finales](endpoint-creation-overview.md)
- [Procedimiento para especificar un enlace de servicio en la configuración](how-to-specify-a-service-binding-in-configuration.md)
- [Procedimiento para especificar un enlace de servicio en el código](how-to-specify-a-service-binding-in-code.md)
- [Procedimiento para especificar un enlace de cliente en la configuración](how-to-specify-a-client-binding-in-configuration.md)
- [Procedimiento para especificar un enlace de cliente en el código](how-to-specify-a-client-binding-in-code.md)
