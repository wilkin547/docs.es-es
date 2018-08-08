---
title: Especificación de una dirección de punto de conexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], addressing
ms.assetid: ac24f5ad-9558-4298-b168-c473c68e819b
ms.openlocfilehash: f7e2253c527cbb2b6f21b222b1e9691c2ecff01f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809123"
---
# <a name="specifying-an-endpoint-address"></a>Especificación de una dirección de punto de conexión
Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de sus extremos. Cada <xref:System.ServiceModel.Description.ServiceEndpoint> contiene un <xref:System.ServiceModel.Description.ServiceEndpoint.Address%2A>, un <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A>y un <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>. El contrato especifica qué operaciones están disponibles. El enlace especifica cómo comunicarse con el servicio y la dirección especifica dónde encontrar el servicio. Cada punto de conexión debe tener una dirección única. La clase <xref:System.ServiceModel.EndpointAddress> representa la dirección de extremo, que contiene un Identificador uniforme de recursos (URI) que representa la dirección del servicio, una <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio, y una colección de <xref:System.ServiceModel.EndpointAddress.Headers%2A>opcional. Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión. Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el extremo un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.  
  
## <a name="definition-of-an-endpoint-address"></a>Definición de una dirección del punto de conexión  
 En WCF, un <xref:System.ServiceModel.EndpointAddress> modela una referencia de extremo (EPR) tal como se define en el estándar WS-Addressing.  
  
 El URI de la dirección de la mayoría de transportes tiene cuatro partes. Por ejemplo, este identificador URI, "http://www.fabrikam.com:322/mathservice.svc/secureEndpoint" tiene las cuatro partes siguientes:  
  
-   Esquema: http:  
  
-   Equipo: www.fabrikam.com  
  
-   (Opcional) Puerto: 322  
  
-   Ruta de acceso: /mathservice.svc/secureEndpoint  
  
 Parte del modelo EPR consiste en que cada referencia de punto de conexión puede llevar algunos parámetros de referencia que agregan información de identificación adicional. En WCF, estos parámetros de referencia se modelan como instancias de la <xref:System.ServiceModel.Channels.AddressHeader> clase.  
  
 La dirección del punto de conexión de un servicio puede especificarse de manera imperativa mediante código, o de manera declarativa mediante configuración. Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio. Generalmente, es más práctico definir extremos de servicio mediante la configuración en lugar del código. Mantener la información del enlace y el direccionamiento fuera del código les permite cambiar sin tener que recompilar e implementar la aplicación. Si no se especifica ningún punto de conexión en el código o en la configuración, el tiempo de ejecución agrega un punto de conexión predeterminado en cada dirección base de cada contrato de servicio implementado por el servicio.  
  
 Hay dos maneras de especificar direcciones de extremo para un servicio de WCF. Puede especificar una dirección absoluta para cada extremo asociado al servicio o puede proporcionar una dirección base para <xref:System.ServiceModel.ServiceHost> de un servicio y, a continuación, especificar una dirección para cada extremo asociado a este servicio que se define relativo a esta dirección base. Puede utilizar cada uno de estos procedimientos para especificar las direcciones de punto de conexión de un servicio mediante configuración o código. Si no especifica una dirección relativa, el servicio utiliza la dirección base. También puede tener varias direcciones base para un servicio, pero en cada servicio se permite sólo una dirección base para cada transporte. Si tiene varios puntos de conexión, cada uno de los cuales está configurado con un enlace diferente, sus direcciones deben ser únicas. Los extremos que utilizan el mismo enlace pero contratos diferentes pueden utilizar la misma dirección.  
  
 Al hospedarse con IIS, no administra por sí mismo las instancias <xref:System.ServiceModel.ServiceHost>. La dirección base siempre es la dirección especificada en el archivo .svc para el servicio al hospedarse en IIS. De modo que siempre debe utilizar direcciones de extremo relativas para los extremos de servicio hospedados en IIS. Proporcionar una dirección de punto de conexión completa puede conducir a errores en la implementación del servicio. Para obtener más información, consulte [implementación de un servicio de WCF Internet Information Services-Hosted](../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="defining-endpoint-addresses-in-configuration"></a>Definición de direcciones de puntos de conexión mediante configuración  
 Para definir un punto de conexión en un archivo de configuración, utilice la [ \<extremo >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.  
  
 [!code-xml[S_UEHelloWorld#5](../../../samples/snippets/common/VS_Snippets_CFX/s_uehelloworld/common/serviceapp2.config#5)]  
  
 Cuando el <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> método se llama (es decir, cuando la aplicación de hospedaje intenta iniciar el servicio), el sistema buscará un [ \<servicio >](../../../docs/framework/configure-apps/file-schema/wcf/service.md) elemento con un atributo de nombre que especifica "UE. Samples.HelloService". Si el [ \<servicio >](../../../docs/framework/configure-apps/file-schema/wcf/service.md) se encuentra el elemento, el sistema carga la clase especificada y crea puntos de conexión mediante las definiciones de punto de conexión proporcionadas en el archivo de configuración. Este mecanismo le permite cargar e iniciar un servicio con dos líneas de código, mientras mantiene la información de enlace y dirección fuera de su código. La ventaja de este enfoque es que estas modificaciones se pueden realizar sin tener que recompilar o implementar la aplicación.  
  
 Los encabezados opcionales se declaran en una [ \<encabezados >](../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md). El siguiente es un ejemplo de los elementos utilizados para especificar los extremos de un servicio en un archivo de configuración que distinga entre dos encabezados: clientes "Gold" de http://tempuri1.org/ y clientes "Standard" de http://tempuri2.org/. El cliente que llame a este servicio debe tener los pertinentes [ \<encabezados >](../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md) en su archivo de configuración.  
  
 [!code-xml[S_UEHelloWorld#1](../../../samples/snippets/common/VS_Snippets_CFX/s_uehelloworld/common/serviceapp.config#1)]  
  
 Los encabezados también se pueden definir como en mensajes individuales en lugar de todos los mensajes en un punto de conexión (como se ha mostrado previamente). Ello se consigue utilizando <xref:System.ServiceModel.OperationContextScope> para crear un nuevo contexto en una aplicación de cliente para agregar un encabezado personalizado al mensaje saliente, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[OperationContextScope#4](../../../samples/snippets/csharp/VS_Snippets_CFX/operationcontextscope/cs/client.cs#4)]
 [!code-vb[OperationContextScope#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationcontextscope/vb/client.vb#4)]  
  
## <a name="endpoint-address-in-metadata"></a>Dirección del punto de conexión en metadatos  
 Una dirección de extremo se representa en el Lenguaje de descripción de servicios Web (WSDL) como un elemento `EndpointReference` (EPR) de WS-Addressing dentro del elemento `wsdl:port` del extremo correspondiente. El EPR contiene la dirección del punto de conexión, así como todas las propiedades de la dirección. Observe que la EPR dentro de `wsdl:port` reemplaza a `soap:Address`, como se observa en el siguiente ejemplo.  
  
  
  
## <a name="defining-endpoint-addresses-in-code"></a>Definición de direcciones del punto de conexión mediante código  
 Una dirección de extremo se puede crear mediante código con la clase <xref:System.ServiceModel.EndpointAddress>. El URI especificado para la dirección del extremo puede ser una ruta de acceso completa o una ruta de acceso relativa a la dirección base del servicio. En el siguiente ejemplo observaremos cómo crear una nueva instancia de la clase <xref:System.ServiceModel.EndpointAddress> y agregarla a la instancia <xref:System.ServiceModel.ServiceHost> que hospeda el servicio.  
  
 En el siguiente ejemplo se muestra cómo se especifica una dirección de punto de conexión completa mediante código.  
  
 [!code-csharp[S_UEHelloWorld#2](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#2)]  
  
 El ejemplo siguiente muestra cómo agregar una dirección relativa ("MyService") a la dirección base del host de servicio.  
  
 [!code-csharp[S_UEHelloWorld#3](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#3)]  
  
> [!NOTE]
>  Las propiedades de <xref:System.ServiceModel.Description.ServiceDescription> en la aplicación de servicio no se deben modificar después del método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ServiceHostBase>. Algunos miembros, como la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> y los métodos `AddServiceEndpoint` en <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.ServiceHost>, inician una excepción si se modifican después de ese punto. Otros permiten modificarlos, pero el resultado no está definido.  
>   
>  De igual forma, en el cliente no se deben modificar los valores <xref:System.ServiceModel.Description.ServiceEndpoint> después de la llamada a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ChannelFactory>. La propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> inicia una excepción si se modifica pasado ese punto. Los otros valores de descripción del cliente pueden modificarse sin el error, pero el resultado no está definido.  
>   
>  Tanto si es para el servicio como para el cliente, se recomienda modificar la descripción antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.  
  
## <a name="using-default-endpoints"></a>Usar puntos de conexión predeterminados  
 Si no se especifica ningún extremo en el código ni en la configuración, el tiempo de ejecución proporciona extremos predeterminados, agregando uno en cada dirección base de cada contrato de servicio implementado por el servicio. La dirección base se puede especificar en el código o en la configuración, y los extremos predeterminados se agregan al llamar al método <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> en el objeto <xref:System.ServiceModel.ServiceHost>.  
  
 Si se proporcionan extremos de forma explícita, es posible agregar extremos predeterminados llamando a <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> en el objeto <xref:System.ServiceModel.ServiceHost> antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Para obtener más información acerca de los puntos de conexión de forma predeterminada, los enlaces y los comportamientos, consulte [configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.EndpointAddress>  
 [Identidad del servicio y autenticación](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Información general sobre la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Hospedar aplicaciones de WPF](../../../docs/framework/wcf/feature-details/hosting.md)
