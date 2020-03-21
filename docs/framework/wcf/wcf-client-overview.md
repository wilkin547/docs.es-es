---
title: Introducción a un cliente WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 7905d540e0f06dd2863cf80381210307e3021918
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183069"
---
# <a name="wcf-client-overview"></a>Introducción a un cliente WCF
En esta sección se describe qué hacen las aplicaciones cliente, cómo configurar, crear y usar un cliente de Windows Communication Foundation (WCF) y cómo proteger las aplicaciones cliente.  
  
## <a name="using-wcf-client-objects"></a>Utilización de objetos cliente WCF  
 Una aplicación cliente es una aplicación administrada que usa un cliente WCF para comunicarse con otra aplicación. Para crear una aplicación cliente para un servicio WCF requiere los pasos siguientes:  
  
1. Obtenga la información del contrato de servicio, el enlace y la dirección del extremo del servicio.  
  
2. Cree un cliente WCF con esa información.  
  
3. Llame a las operaciones.  
  
4. Cierre el objeto de cliente WCF.  
  
 Las siguientes secciones explican estos pasos y proporcionan una breve introducción a las siguientes cuestiones:  
  
- Control de errores  
  
- Configuración y protección de los clientes.  
  
- Creación de objetos de devolución de llamada para los servicios dúplex.  
  
- Llamada asincrónica a los servicios.  
  
- Llamada a los servicios mediante los canales cliente.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Obtención del contrato de servicios, los enlaces y las direcciones  
 En WCF, los servicios y los clientes modelan contratos mediante atributos administrados, interfaces y métodos. Para conectar con un servicio en una aplicación cliente, es necesario obtener la información del tipo de contrato de servicios. Normalmente, esto se hace mediante la herramienta de utilidad de metadatos de [ServiceModel (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md)que descarga metadatos del servicio, lo convierte en un archivo de código fuente administrado en el idioma de su elección y crea un archivo de configuración de aplicación cliente que puede usar para configurar el objeto de cliente WCF. Por ejemplo, si va a crear un objeto `MyCalculatorService`de cliente WCF para invocar un , `http://computerName/MyCalculatorService/Service.svc?wsdl`y sabe que los metadatos de ese servicio `ClientCode.vb` se publican en , el ejemplo de código siguiente muestra cómo usar Svcutil.exe para obtener un archivo que contiene el contrato de servicio en código administrado.  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Puede compilar este código de contrato en la aplicación cliente o en otro ensamblado que la aplicación cliente puede usar para crear un objeto de cliente WCF. Puede utilizar el archivo de configuración y configurar el objeto de cliente para conectarse correctamente con el servicio.  
  
 Para obtener un ejemplo de este proceso, vea [Cómo: Crear un cliente](how-to-create-a-wcf-client.md). Para obtener información más completa sobre los contratos, consulte [Contratos](./feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Creación de un objeto de cliente de WCF  
 Un cliente WCF es un objeto local que representa un servicio WCF en un formulario que el cliente puede usar para comunicarse con el servicio remoto. Los tipos de cliente WCF implementan el contrato de servicio de destino, por lo que al crear uno y configurarlo, puede usar el objeto de cliente directamente para invocar operaciones de servicio. El tiempo de ejecución de WCF convierte las llamadas al método en mensajes, los envía al servicio, `out` escucha `ref` la respuesta y devuelve esos valores al objeto de cliente WCF como valores devueltos o parámetros.  
  
 También puede usar objetos de canal de cliente WCF para conectarse con y usar servicios. Para obtener más información, vea [Arquitectura de cliente WCF](./feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Creación de un nuevo objeto WCF  
 Para mostrar la utilización de una clase <xref:System.ServiceModel.ClientBase%601>, supongamos que el siguiente contrato de servicio simple se ha generado a partir de una aplicación de servicio.  
  
> [!NOTE]
> Si usa Visual Studio para crear el cliente WCF, los objetos se cargan automáticamente en el explorador de objetos al agregar una referencia de servicio al proyecto.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Si no usa Visual Studio, examine el código de contrato <xref:System.ServiceModel.ClientBase%601> generado para buscar `ISampleService`el tipo que se extiende y la interfaz de contrato de servicio. En este caso, ese tipo es similar al código siguiente:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Esta clase puede crearse como un objeto local, mediante uno de los constructores, configurarse y, a continuación, utilizarse para la conexión con un servicio del tipo `ISampleService`.  
  
 Se recomienda crear primero el objeto de cliente WCF y, a continuación, usarlo y cerrarlo dentro de un único bloque try/catch. No debe usar `using` la`Using` instrucción ( en Visual Basic) porque puede enmascarar excepciones en determinados modos de error. Para obtener más información, vea las secciones siguientes, así como Usar cerrar y anular para liberar recursos de [cliente WCF.](./samples/use-close-abort-release-wcf-client-resources.md)  
  
### <a name="contracts-bindings-and-addresses"></a>Contratos, enlaces y direcciones  
 Para poder crear un objeto de cliente WCF, debe configurar el objeto de cliente. En concreto, debe tener un punto de *conexión* de servicio para usar. Un punto de conexión es la combinación de un contrato de servicio, un enlace y una dirección. (Para obtener más información acerca de los puntos de conexión, vea [puntos de conexión: direcciones, enlaces y contratos](./feature-details/endpoints-addresses-bindings-and-contracts.md).) Normalmente, esta información se [ \<](../configure-apps/file-schema/wcf/endpoint-of-client.md) encuentra en el extremo>elemento de un archivo de configuración de la aplicación cliente, como el que genera la herramienta Svcutil.exe y se carga automáticamente al crear el objeto de cliente. Ambos tipos de cliente WCF también tienen sobrecargas que permiten especificar esta información mediante programación.  
  
 Por ejemplo, un archivo de configuración generado para el `ISampleService` utilizado en los ejemplos anteriores, contiene la información de extremo siguiente.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Este archivo de configuración especifica un punto de conexión de destino en el elemento `<client>`. Para obtener más información sobre el <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> uso <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> de varios extremos de destino, vea los constructores o los constructores.  
  
## <a name="calling-operations"></a>Llamadas a operaciones  
 Una vez que haya creado y configurado un objeto de cliente, cree un bloque try/catch, llame a las operaciones de la misma manera que lo haría si el objeto fuera local y cierre el objeto de cliente WCF. Cuando la aplicación cliente llama a la primera operación, WCF abre automáticamente el canal subyacente y el canal subyacente se cierra cuando se recicla el objeto. (De manera alternativa, también puede abrir y cerrar explícitamente el canal antes o después de llamar a otras operaciones).  
  
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
  
 Puede llamar a operaciones mediante la creación de un objeto de cliente WCF y llamar a sus métodos, como se muestra en el ejemplo de código siguiente. Tenga en cuenta que la apertura, llamada y cierre del objeto de cliente WCF se produce dentro de un único bloque try/catch. Para obtener más información, vea [Acceso a servicios mediante un cliente WCF](./feature-details/accessing-services-using-a-client.md) y Usar cerrar y anular para liberar recursos de cliente [WCF](./samples/use-close-abort-release-wcf-client-resources.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Control de errores  
 Las excepciones pueden producirse en una aplicación cliente cuando se abre el canal de cliente subyacente (explícita o automáticamente mediante la llamada a una operación), se utiliza el cliente u objeto de canal para llamar a las operaciones, o se cierra el canal de cliente subyacente. Se recomienda como mínimo que las aplicaciones prevean administrar posibles <xref:System.TimeoutException?displayProperty=nameWithType> y las excepciones <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>, además de cualquier objeto <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> iniciado como resultado de los errores de SOAP devueltos por las operaciones. Los errores de SOAP especificados en el contrato de operación se elevan a las aplicaciones cliente como <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, donde el parámetro de tipo es el tipo de detalle del error de SOAP. Para obtener más información sobre el control de condiciones de error en una aplicación cliente, vea [Enviar y recibir errores](sending-and-receiving-faults.md). Para obtener un ejemplo completo de cómo controlar los errores en un cliente, vea [Excepciones esperadas](./samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Configuración y protección de clientes.  
 La configuración de un cliente se inicia con la carga de información de extremo de destino necesaria para el cliente u objeto de canal, normalmente desde un archivo de configuración, aunque también puede cargarse esta información mediante programación utilizando los constructores y propiedades de cliente. No obstante, son necesarios pasos de configuración adicionales que habiliten cierto comportamiento del cliente y diferentes escenarios de seguridad.  
  
 Por ejemplo, los requisitos de seguridad para los contratos de servicios se declaran en la interfaz del contrato de servicio; si Svcutil.exe creó un archivo de configuración, ese archivo contiene, normalmente, un enlace capaz de admitir los requisitos de seguridad del servicio. En algunos casos, sin embargo, puede ser necesaria una mayor configuración de seguridad, como la configuración de credenciales de cliente. Para obtener información completa acerca de la configuración de seguridad para los clientes WCF, vea [proteger clientes](securing-clients.md).  
  
 Además, algunas modificaciones personalizadas se pueden habilitar en aplicaciones cliente, como comportamientos en tiempo de ejecución personalizados. Para obtener más información acerca de cómo configurar un comportamiento de cliente personalizado, vea [Configuración de comportamientos](configuring-client-behaviors.md)de cliente .  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Creación de objetos de devolución de llamada para servicios dúplex.  
 Los servicios dúplex especifican un contrato de devolución de llamada que la aplicación cliente debe implementar para proporcionar un objeto de devolución de llamada, y que el servicio realice las llamadas según los requisitos del contrato. Aunque los objetos de devolución de llamada no son servicios completos (por ejemplo, no puede iniciar un canal con un objeto de devolución de llamada), en lo que respecta la implementación y la configuración pueden concebirse como un tipo de servicio.  
  
 Los clientes de servicios dúplex deben:  
  
- Implementar una clase de contrato de devolución de llamada.  
  
- Cree una instancia de la clase de implementación del contrato de devolución de llamada y úsela para crear el <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> objeto que se pasa al constructor de cliente WCF.  
  
- Invocar operaciones y controlar las devoluciones de llamada de la operación.  
  
 Los objetos de cliente WCF dúplex funcionan como sus homólogos no dúplex, con la excepción de que exponen la funcionalidad necesaria para admitir devoluciones de llamada, incluida la configuración del servicio de devolución de llamada.  
  
 Por ejemplo, pueden controlarse distintos aspectos del comportamiento del tiempo de ejecución del objeto de devolución de llamada mediante las propiedades del atributo <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>, en la clase de devolución de llamada. Otro ejemplo es el uso de la clase <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> para habilitar el retorno de información de excepción a los servicios que llaman al objeto de devolución de llamada. Para obtener más información, consulte [Servicios dúplex](./feature-details/duplex-services.md). Para obtener un ejemplo completo, consulte [Dúplex](./samples/duplex.md).  
  
 En los equipos de Windows XP que ejecutan Internet Information Services (IIS) 5.1, los clientes dúplex deben especificar una dirección base de cliente utilizando la clase <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, o se iniciará una excepción. En el ejemplo de código siguiente se muestra cómo realizar esta especificación en el código.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 El código siguiente muestra cómo realizar esta especificación en un archivo de configuración  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Llamada a servicios de manera asincrónica.  
 La manera cómo se realizan las llamadas a las operaciones depende del desarrollador cliente. La razón es que los mensajes que constituyen una operación pueden asignarse a métodos sincrónicos o asincrónicos cuando se expresan en código administrado. Por consiguiente, si desea crear un cliente que llama a las operaciones de manera asincrónica, puede utilizar Svcutil.exe para generar código de cliente asincrónico mediante la opción `/async`. Para obtener más información, vea [Cómo: llamar a operaciones](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)de servicio de forma asincrónica.  
  
## <a name="calling-services-using-wcf-client-channels"></a>Llamada a los servicios mediante canales de cliente WCF.  
 Los tipos <xref:System.ServiceModel.ClientBase%601>de cliente WCF <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> se extienden, que a su vez deriva de la interfaz para exponer el sistema de canal subyacente. Puede invocar los servicios utilizando el contrato de servicios de destino con la clase <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Para obtener más información, vea [Arquitectura de cliente WCF](./feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
