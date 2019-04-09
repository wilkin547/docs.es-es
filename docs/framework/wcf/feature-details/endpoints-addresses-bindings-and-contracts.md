---
title: 'Puntos de conexión: direcciones, enlaces y contratos'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3e78e7cf0c5acde53d7ee23294fd52134414e860
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207531"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Puntos de conexión: direcciones, enlaces y contratos
Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de la *extremos* del servicio. Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.  
  
 Cada punto de conexión está compuesto de cuatro propiedades:  
  
-   Una dirección que indica dónde se puede encontrar el punto de conexión.  
  
-   Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.  
  
-   Un contrato que identifica las operaciones disponibles.  
  
-   Un conjunto de comportamientos que especifican detalles de implementación local del punto de conexión.  
  
 En este tema se describe esta estructura de punto de conexión y se explica cómo se representa en el modelo de objetos WCF.  
  
## <a name="the-structure-of-an-endpoint"></a>Estructura de un extremo  
 Cada punto de conexión está compuesto de lo siguiente:  
  
-   Dirección: La dirección identifica el punto de conexión y le indica a posibles consumidores del servicio donde se encuentra. Se representa en el modelo de objetos WCF mediante el <xref:System.ServiceModel.EndpointAddress> clase. Una clase <xref:System.ServiceModel.EndpointAddress> contiene:  
  
    -   Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.  
  
    -   Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales. Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el extremo.  
  
     Para obtener más información, consulte [especificando una dirección de extremo](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   Enlace: El enlace especifica cómo comunicarse con el punto de conexión. Esto incluye:  
  
    -   El protocolo de transporte que se ha de utilizar (por ejemplo, TCP o HTTP).  
  
    -   La codificación que se ha de utilizar para los mensajes (por ejemplo, texto o binario).  
  
    -   Los requisitos de seguridad necesarios (por ejemplo, SSL o seguridad de mensaje SOAP).  
  
     Para obtener más información, consulte [información general sobre los enlaces de WCF](../../../../docs/framework/wcf/bindings-overview.md). Un enlace se representa en el modelo de objetos WCF mediante la clase base abstracta <xref:System.ServiceModel.Channels.Binding>. Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema. Para obtener más información, consulte [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
-   Contratos: El contrato describe qué funcionalidad expone el punto de conexión al cliente. Un contrato especifica:  
  
    -   Qué operaciones puede llamar un cliente.  
  
    -   La forma del mensaje.  
  
    -   El tipo de parámetros de entrada o datos requeridos para llamar a la operación.  
  
    -   Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.  
  
     Para obtener más información acerca de cómo definir un contrato, vea [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
-   Comportamientos: Puede utilizar los comportamientos de extremo para personalizar el comportamiento del extremo del servicio local. Para ello, los comportamientos de extremo que participan en el proceso de creación de un WCFruntime. Un ejemplo de un comportamiento de punto de conexión es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web (WSDL). Para obtener más información, consulte [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## <a name="defining-endpoints"></a>Definición de extremos  
 Puede especificar el extremo de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración. Para obtener más información, vea [Cómo: Crear un punto de conexión de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) y [Cómo: Crear un punto de conexión de servicio en código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## <a name="in-this-section"></a>En esta sección  
 En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.  
  
 [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Describe cómo se direccionan los puntos de conexión en WCF.  
  
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.  
  
 [Contratos](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Describe cómo los contratos definen los métodos de un servicio.  
  
 [Filtrar para crear un punto de conexión de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Describe cómo crear un punto de conexión de servicio mediante configuración  
  
 [Filtrar para crear un punto de conexión de servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Describe cómo crear un extremo de servicio mediante código.  
  
 [Filtrar para usar Svcutil.exe para validar el código del servicio compilado](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Describe cómo detectar errores en las implementaciones de servicio y configuraciones sin hospedar el servicio mediante el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="see-also"></a>Vea también

- [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)
- [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)
