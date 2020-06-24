---
title: 'Puntos de conexión: direcciones, enlaces y contratos'
description: Obtenga información acerca de cómo se produce toda comunicación con un servicio WCF a través de los puntos de conexión de servicio, que proporcionan a los clientes acceso a la funcionalidad que ofrece el servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247317"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Puntos de conexión: direcciones, enlaces y contratos

Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de los *extremos* del servicio. Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.

Cada punto de conexión está compuesto de cuatro propiedades:

- Una dirección que indica dónde se puede encontrar el punto de conexión.

- Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.

- Un contrato que identifica las operaciones disponibles.

- Un conjunto de comportamientos que especifican detalles de implementación local del punto de conexión.

En este tema se describe esta estructura de extremos y se explica cómo se representa en el modelo de objetos WCF.

## <a name="the-structure-of-an-endpoint"></a>Estructura de un extremo

Cada punto de conexión está compuesto de lo siguiente:

- Dirección: la dirección identifica únicamente el punto de conexión e indica a los consumidores potenciales del servicio dónde se ubica éste. Se representa en el modelo de objetos WCF mediante la <xref:System.ServiceModel.EndpointAddress> clase. Una clase <xref:System.ServiceModel.EndpointAddress> contiene:

  - Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.

  - Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales. Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el extremo.

  Para obtener más información, vea [especificar una dirección de extremo](../specifying-an-endpoint-address.md).

- Enlace: el enlace especifica cómo comunicarse con el extremo. Esto incluye:

  - El protocolo de transporte que se ha de utilizar (por ejemplo, TCP o HTTP).

  - La codificación que se ha de utilizar para los mensajes (por ejemplo, texto o binario).

  - Los requisitos de seguridad necesarios (por ejemplo, SSL o seguridad de mensaje SOAP).

  Para obtener más información, vea [información general sobre los enlaces de WCF](../bindings-overview.md). La clase base abstracta representa un enlace en el modelo de objetos de WCF <xref:System.ServiceModel.Channels.Binding> . Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema. Para obtener más información, vea [enlaces proporcionados por el sistema](../system-provided-bindings.md).

- Contratos: el contrato describe qué funcionalidad expone el punto de conexión al cliente. Un contrato especifica:

  - Qué operaciones puede llamar un cliente.

  - La forma del mensaje.

  - El tipo de parámetros de entrada o datos requeridos para llamar a la operación.

  - Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.

  Para obtener más información sobre cómo definir un contrato, consulte [diseño de contratos de servicio](../designing-service-contracts.md).

- Comportamientos: puede utilizar los comportamientos de punto de conexión para personalizar el comportamiento local del punto de conexión de servicio. Los comportamientos del punto de conexión logran esto participando en el proceso de compilación de un tiempo de ejecución de WCF. Un ejemplo de un comportamiento de punto de conexión es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web (WSDL). Para obtener más información, vea [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).

## <a name="defining-endpoints"></a>Definición de extremos

Puede especificar el extremo de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración. Para obtener más información, vea [Cómo: crear un punto de conexión de servicio en la configuración](how-to-create-a-service-endpoint-in-configuration.md) y [Cómo: crear un punto de conexión de servicio en el código](how-to-create-a-service-endpoint-in-code.md).

## <a name="in-this-section"></a>En esta sección

En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.

[Corrige](endpoint-addresses.md)\
Describe cómo se abordan los extremos en WCF.

[Enlaces](bindings.md)\
Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.

[Trata](contracts.md)\
Describe cómo los contratos definen los métodos de un servicio.

[Cómo: crear un punto de conexión de servicio en la configuración](how-to-create-a-service-endpoint-in-configuration.md)\
Describe cómo crear un punto de conexión de servicio mediante configuración

[Cómo: crear un punto de conexión de servicio en el código](how-to-create-a-service-endpoint-in-code.md)\
Describe cómo crear un extremo de servicio mediante código.

[Cómo: usar Svcutil.exe para validar el código de servicio compilado](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)\
Describe cómo detectar errores en las implementaciones de servicio y las configuraciones sin hospedar el servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).

## <a name="see-also"></a>Vea también

- [Configuración de servicios](../configuring-services.md)
- [Extensión de enlaces](../extending/extending-bindings.md)
