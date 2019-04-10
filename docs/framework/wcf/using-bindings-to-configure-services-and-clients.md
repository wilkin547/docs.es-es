---
title: Utilización de enlaces para configurar servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
ms.openlocfilehash: 3b4f00617418d5f84a0da5d0e531e1f671b58bb1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323153"
---
# <a name="using-bindings-to-configure-services-and-clients"></a>Utilización de enlaces para configurar servicios y clientes
Los enlaces son los objetos que especifican los datos de comunicación exigidos para conectar a un punto de conexión. Más específicamente, los enlaces contienen información de configuración utilizada para crear el cliente o servicio en tiempo de ejecución mediante la definición de las características de transportes, formatos de la conexión (codificación de mensajes) y protocolos que se utilizarán en el punto de conexión respectivo o canal de cliente. Para crear un servicio de Windows Communication Foundation (WCF) funcione, cada punto de conexión en el servicio requiere un enlace. Este tema explica qué enlaces son, cómo se definen, y cómo se especifica un enlace determinado para un punto de conexión.  
  
## <a name="what-a-binding-defines"></a>Qué define un enlace  
 La información de un enlace puede ser muy básica o muy compleja. El enlace más básico especifica solo el protocolo de transporte (como HTTP) que se debe utilizar para conectar al extremo. Más generalmente, la información que contiene un enlace sobre cómo conectarse a un extremo queda incluida en una de las categorías de la tabla siguiente.  
  
 Protocolos  
 Determina el mecanismo de seguridad utilizado, función de la mensajería de confianza o configuración de flujo de contexto de transacción.  
  
 Transporte  
 Determina el protocolo de transporte subyacente que se utilizará (por ejemplo, TCP o HTTP).  
  
 Codificación  
 Determina la codificación del mensaje, por ejemplo, texto/XML, binario o Mecanismo de optimización de transmisión del mensaje (MTOM), que determinan cómo se representan los mensajes como secuencias de bytes en la conexión.  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  
 WCF incluye un conjunto de enlaces proporcionados por el sistema que están diseñados para cubrir la mayoría de los escenarios y requisitos de la aplicación. Las clases siguientes representan algunos ejemplos de enlaces proporcionados por el sistema:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: Un protocolo HTTP enlace adecuado para conectarse a servicios Web que se ajusta a WS-I Basic Profile 1.1 especificación (por ejemplo, los servicios Web ASP.NET [ASMX]-servicios basados en).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: Protocolos de especificaciones de servicios de un protocolo HTTP conveniente para conectar a los puntos de conexión que se ajustan a la Web de enlace.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Usa la codificación binaria .NET y tramas tecnologías junto con el transporte de canalización con nombre de Windows para conectarse a otros extremos WCF en el mismo equipo.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: Usa la codificación binaria .NET y las tecnologías junto con el Message Queuing (también conocido como MSMQ) trama para crear las conexiones de mensajes en cola con otros extremos WCF.  
  
 Para obtener una lista completa de los enlaces proporcionados por el sistema, con descripciones, consulte [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Enlaces personalizados  
 Si la colección de enlaces proporcionada por el sistema no tiene la combinación correcta de características que necesita una aplicación de servicio, puede crear un enlace <xref:System.ServiceModel.Channels.CustomBinding>. Para obtener más información acerca de los elementos de un <xref:System.ServiceModel.Channels.CustomBinding> enlace, vea [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) y [enlaces personalizados](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="using-bindings"></a>Utilizar los enlaces  
 El uso de enlaces conlleva dos pasos básicos:  
  
1. Seleccione o defina un enlace. El método más fácil es elegir uno de los enlaces proporcionados por el sistema y utilizar su configuración predeterminada. Puede elegir también un enlace proporcionado por el sistema y restablecer sus valores de propiedad para satisfacer sus necesidades También puede crear un enlace personalizado y establecer las propiedades como necesite.  
  
2. Cree un punto de conexión que utiliza este enlace.  
  
## <a name="code-and-configuration"></a>Código y configuración  
 Puede definir o configurar los enlaces a través del código o configuración. Estos dos enfoques son independientes según el tipo de enlace utilizado, por ejemplo, si utiliza un enlace proporcionado por el sistema o un enlace <xref:System.ServiceModel.Channels.CustomBinding>. En general, el uso de código proporciona un control total sobre la definición de un enlace cuando se compila. Con la configuración, por otro lado, permite que un administrador del sistema o el usuario de un servicio WCF o cliente cambiar los parámetros de enlaces. Esta flexibilidad es a menudo deseable porque no hay ninguna manera de predecir los requisitos específicos del equipo y condiciones en la que una aplicación de WCF es implementar la red. Separar la información de enlace (y direccionamiento) del código permite a los administradores cambiar los datos obligatorios sin tener que recompilar o implementar de nuevo la aplicación. Tenga en cuenta que si el enlace se define en código, sobrescribe las definiciones basadas en configuración realizadas en el archivo de configuración. Para obtener ejemplos de estos enfoques, consulte los temas siguientes:  
  
-   [Cómo: Hospedar un servicio WCF en una aplicación administrada](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md) proporciona un ejemplo de cómo crear un enlace en código.  
  
-   [Tutorial: Crear un cliente de Windows Communication Foundation](../../../docs/framework/wcf/how-to-create-a-wcf-client.md) proporciona un ejemplo de creación de un cliente mediante configuración.  
  
## <a name="see-also"></a>Vea también

- [Información general acerca de la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Filtrar para especificar un enlace de servicio en la configuración](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Filtrar para especificar un enlace de servicio en el código](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
- [Filtrar para especificar un enlace de cliente en la configuración](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
- [Filtrar para especificar un enlace de cliente en el código](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-code.md)
