---
title: Introducción a un cliente WCF
description: Obtenga información sobre qué hacen las aplicaciones cliente, cómo configurar, crear y usar un cliente de WCF y cómo proteger las aplicaciones cliente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: c66541f95d04373a9a29fafe58528872335936c4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245920"
---
# <a name="wcf-client-overview"></a>Información general del cliente de WCF

En esta sección se describe qué hacen las aplicaciones cliente, cómo configurar, crear y usar un cliente de Windows Communication Foundation (WCF) y cómo proteger las aplicaciones cliente.  
  
## <a name="using-wcf-client-objects"></a>Utilización de objetos cliente WCF  
 Una aplicación cliente es una aplicación administrada que utiliza un cliente WCF para comunicarse con otra aplicación. La creación de una aplicación cliente para un servicio WCF requiere los pasos siguientes:  
  
1. Obtenga la información del contrato de servicio, el enlace y la dirección del extremo del servicio.  
  
2. Cree un cliente WCF con esa información.  
  
3. Llame a las operaciones.  
  
4. Cierre el objeto de cliente de WCF.  
  
Las siguientes secciones explican estos pasos y proporcionan una breve introducción a las siguientes cuestiones:  
  
- Control de errores  
  
- Configuración y protección de los clientes.  
  
- Creación de objetos de devolución de llamada para los servicios dúplex.  
  
- Llamada asincrónica a los servicios.  
  
- Llamada a los servicios mediante los canales cliente.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Obtención del contrato de servicios, los enlaces y las direcciones  
 En WCF, los servicios y clientes modelan los contratos mediante atributos, interfaces y métodos administrados. Para conectar con un servicio en una aplicación cliente, es necesario obtener la información del tipo de contrato de servicios. Normalmente, se obtiene información de tipo para el contrato de servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md). La utilidad descarga los metadatos del servicio, los convierte en un archivo de código fuente administrado en el idioma de su elección y crea un archivo de configuración de aplicación cliente que puede usar para configurar el objeto de cliente de WCF. Por ejemplo, si va a crear un objeto de cliente de WCF para invocar un `MyCalculatorService` y sabe que los metadatos de ese servicio se publican en `http://computerName/MyCalculatorService/Service.svc?wsdl` , en el ejemplo de código siguiente se muestra cómo usar Svcutil.exe para obtener un `ClientCode.vb` archivo que contiene el contrato de servicios en código administrado.  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Puede compilar este código de contrato en la aplicación cliente o en otro ensamblado que la aplicación cliente pueda utilizar para crear un objeto de cliente de WCF. Puede utilizar el archivo de configuración y configurar el objeto de cliente para conectarse correctamente con el servicio.  
  
 Para obtener un ejemplo de este proceso, consulte [Cómo: crear un cliente](how-to-create-a-wcf-client.md). Para obtener información más completa acerca de los contratos, consulte [contratos](./feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Creación de un objeto de cliente de WCF  
 Un cliente WCF es un objeto local que representa un servicio WCF en un formulario que el cliente puede utilizar para comunicarse con el servicio remoto. Los tipos de cliente de WCF implementan el contrato de servicio de destino, por lo que cuando se crea uno y se configura, se puede usar el objeto de cliente directamente para invocar operaciones de servicio. El tiempo de ejecución de WCF convierte las llamadas de método en mensajes, las envía al servicio, escucha la respuesta y devuelve esos valores al objeto de cliente de WCF como valores devueltos `out` o `ref` parámetros.  
  
 También puede utilizar objetos de canal de cliente WCF para conectarse con los servicios y utilizarlos. Para obtener más información, consulte la [arquitectura de cliente de WCF](./feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Creación de un nuevo objeto WCF  
 Para mostrar la utilización de una clase <xref:System.ServiceModel.ClientBase%601>, supongamos que el siguiente contrato de servicio simple se ha generado a partir de una aplicación de servicio.  
  
> [!NOTE]
> Si usa Visual Studio para crear el cliente de WCF, los objetos se cargan automáticamente en el examinador de objetos al agregar una referencia de servicio al proyecto.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Si no usa Visual Studio, examine el código de contrato generado para encontrar el tipo que extiende <xref:System.ServiceModel.ClientBase%601> y la interfaz del contrato de servicio `ISampleService` . En este caso, ese tipo es similar al código siguiente:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Esta clase puede crearse como un objeto local, mediante uno de los constructores, configurarse y, a continuación, utilizarse para la conexión con un servicio del tipo `ISampleService`.  
  
 Se recomienda crear el objeto de cliente de WCF primero y, a continuación, usarlo y cerrarlo dentro de un solo bloque try/catch. No use la `using` instrucción ( `Using` en Visual Basic) porque puede enmascarar excepciones en ciertos modos de error. Para obtener más información, vea las secciones siguientes, así como el [uso de Close y Abort para liberar los recursos de cliente de WCF](./samples/use-close-abort-release-wcf-client-resources.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Contratos, enlaces y direcciones  
 Para poder crear un objeto de cliente de WCF, debe configurar el objeto de cliente. En concreto, debe tener un *punto de conexión* de servicio para utilizar. Un punto de conexión es la combinación de un contrato de servicio, un enlace y una dirección. (Para obtener más información sobre los puntos de conexión, vea [puntos de conexión: direcciones, enlaces y contratos](./feature-details/endpoints-addresses-bindings-and-contracts.md)). Normalmente, esta información se encuentra en el [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento de un archivo de configuración de la aplicación cliente, como el que genera la herramienta de Svcutil.exe, y se carga automáticamente al crear el objeto de cliente. Ambos tipos de cliente de WCF también tienen sobrecargas que permiten especificar esta información mediante programación.  
  
 Por ejemplo, un archivo de configuración generado para el `ISampleService` utilizado en los ejemplos anteriores, contiene la información de extremo siguiente.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Este archivo de configuración especifica un punto de conexión de destino en el elemento `<client>`. Para obtener más información sobre el uso de varios puntos de conexión de destino, vea los <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> constructores o.  
  
## <a name="calling-operations"></a>Llamadas a operaciones  
 Una vez creado y configurado un objeto de cliente, cree un bloque try/catch, llame a las operaciones del mismo modo que si el objeto fuera local y cierre el objeto de cliente de WCF. Cuando la aplicación cliente llama a la primera operación, WCF abre automáticamente el canal subyacente y el canal subyacente se cierra cuando se recicla el objeto. (De manera alternativa, también puede abrir y cerrar explícitamente el canal antes o después de llamar a otras operaciones).  
  
 Por ejemplo, si posee el siguiente contrato de servicio:  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _
   Public Interface ICalculator  
        <OperationContract> _
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 Puede llamar a las operaciones creando un objeto de cliente de WCF y llamando a sus métodos, como se muestra en el ejemplo de código siguiente. La apertura, llamada y cierre del objeto de cliente de WCF se produce dentro de un único bloque try/catch. Para obtener más información, vea [obtener acceso a servicios mediante un cliente WCF](./feature-details/accessing-services-using-a-client.md) y [usar Close y Abort para liberar los recursos de cliente de WCF](./samples/use-close-abort-release-wcf-client-resources.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Control de errores  
 Las excepciones pueden producirse en una aplicación cliente cuando se abre el canal de cliente subyacente (explícita o automáticamente mediante la llamada a una operación), se utiliza el cliente u objeto de canal para llamar a las operaciones, o se cierra el canal de cliente subyacente. Se recomienda como mínimo que las aplicaciones prevean administrar posibles <xref:System.TimeoutException?displayProperty=nameWithType> y las excepciones <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>, además de cualquier objeto <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> iniciado como resultado de los errores de SOAP devueltos por las operaciones. Los errores de SOAP especificados en el contrato de operación se elevan a las aplicaciones cliente como <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, donde el parámetro de tipo es el tipo de detalle del error de SOAP. Para obtener más información sobre cómo controlar las condiciones de error en una aplicación cliente, consulte [envío y recepción de errores](sending-and-receiving-faults.md). Para obtener un ejemplo completo que muestra cómo controlar los errores en un cliente, consulte [excepciones esperadas](./samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Configuración y protección de clientes.  
 La configuración de un cliente se inicia con la carga de información de extremo de destino necesaria para el cliente u objeto de canal, normalmente desde un archivo de configuración, aunque también puede cargarse esta información mediante programación utilizando los constructores y propiedades de cliente. No obstante, son necesarios pasos de configuración adicionales que habiliten cierto comportamiento del cliente y diferentes escenarios de seguridad.  
  
 Por ejemplo, los requisitos de seguridad para los contratos de servicios se declaran en la interfaz del contrato de servicio; si Svcutil.exe creó un archivo de configuración, ese archivo contiene, normalmente, un enlace capaz de admitir los requisitos de seguridad del servicio. En algunos casos, sin embargo, puede ser necesaria una mayor configuración de seguridad, como la configuración de credenciales de cliente. Para obtener información completa sobre la configuración de seguridad para los clientes de WCF, consulte [protección de clientes](securing-clients.md).  
  
 Además, algunas modificaciones personalizadas se pueden habilitar en aplicaciones cliente, como comportamientos en tiempo de ejecución personalizados. Para obtener más información sobre cómo configurar un comportamiento de cliente personalizado, vea [configurar comportamientos de cliente](configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Creación de objetos de devolución de llamada para servicios dúplex.  
 Los servicios dúplex especifican un contrato de devolución de llamada que la aplicación cliente debe implementar para proporcionar un objeto de devolución de llamada, y que el servicio realice las llamadas según los requisitos del contrato. Aunque los objetos de devolución de llamada no son servicios completos (por ejemplo, no puede iniciar un canal con un objeto de devolución de llamada), en lo que respecta la implementación y la configuración pueden concebirse como un tipo de servicio.  
  
 Los clientes de servicios dúplex deben:  
  
- Implementar una clase de contrato de devolución de llamada.  
  
- Cree una instancia de la clase de implementación de contrato de devolución de llamada y Úsela para crear el <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> objeto que se pasa al constructor de cliente de WCF.  
  
- Invocar operaciones y controlar las devoluciones de llamada de la operación.  
  
 Los objetos de cliente WCF dúplex funcionan como sus homólogos no dúplex, con la excepción de que exponen la funcionalidad necesaria para admitir las devoluciones de llamada, incluida la configuración del servicio de devolución de llamada.  
  
 Por ejemplo, pueden controlarse distintos aspectos del comportamiento del tiempo de ejecución del objeto de devolución de llamada mediante las propiedades del atributo <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>, en la clase de devolución de llamada. Otro ejemplo es el uso de la clase <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> para habilitar el retorno de información de excepción a los servicios que llaman al objeto de devolución de llamada. Para obtener más información, vea [servicios dúplex](./feature-details/duplex-services.md). Para obtener un ejemplo completo, vea [dúplex](./samples/duplex.md).  
  
 En los equipos de Windows XP que ejecutan Internet Information Services (IIS) 5.1, los clientes dúplex deben especificar una dirección base de cliente utilizando la clase <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, o se iniciará una excepción. En el ejemplo de código siguiente se muestra cómo realizar esta especificación en el código.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 El código siguiente muestra cómo realizar esta especificación en un archivo de configuración  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Llamada a servicios de manera asincrónica.  
 La manera cómo se realizan las llamadas a las operaciones depende del desarrollador cliente. La razón es que los mensajes que constituyen una operación pueden asignarse a métodos sincrónicos o asincrónicos cuando se expresan en código administrado. Por consiguiente, si desea crear un cliente que llama a las operaciones de manera asincrónica, puede utilizar Svcutil.exe para generar código de cliente asincrónico mediante la opción `/async`. Para obtener más información, vea [Cómo: llamar a las operaciones de servicio de forma asincrónica](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Llamada a los servicios mediante canales de cliente WCF.  
 Los tipos de cliente de WCF extienden <xref:System.ServiceModel.ClientBase%601> , que a su vez deriva de <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> la interfaz para exponer el sistema del canal subyacente. Puede invocar los servicios utilizando el contrato de servicios de destino con la clase <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Para obtener más información, consulte la [arquitectura de cliente de WCF](./feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
