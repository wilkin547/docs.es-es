---
title: Introducción a un cliente WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7f083ea44b9bdbd9bf85d65c42d663d87af8d812
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="wcf-client-overview"></a>Introducción a un cliente WCF
En esta sección se describe qué aplicaciones pueden configurar un cliente [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], cómo lo configuran, crean y utilizan, y cómo proteger las aplicaciones cliente.  
  
## <a name="using-wcf-client-objects"></a>Utilización de objetos cliente WCF  
 Una aplicación cliente es una aplicación administrada que utiliza un cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para comunicarse con otra aplicación. Para crear la aplicación cliente de un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es necesario seguir los pasos siguientes:  
  
1.  Obtenga la información del contrato de servicio, el enlace y la dirección del extremo del servicio.  
  
2.  Cree un cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] utilizando dicha información.  
  
3.  Llame a las operaciones.  
  
4.  Cierre el objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Las siguientes secciones explican estos pasos y proporcionan una breve introducción a las siguientes cuestiones:  
  
-   Control de errores  
  
-   Configuración y protección de los clientes.  
  
-   Creación de objetos de devolución de llamada para los servicios dúplex.  
  
-   Llamada asincrónica a los servicios.  
  
-   Llamada a los servicios mediante los canales cliente.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Obtención del contrato de servicios, los enlaces y las direcciones  
 En [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], los servicios y clientes modelan los contratos utilizando los atributos, interfaces y métodos administrados. Para conectar con un servicio en una aplicación cliente, es necesario obtener la información del tipo de contrato de servicios. Normalmente, esto se realiza mediante el uso de la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), que descarga los metadatos del servicio, lo convierte en un archivo de código fuente administrado en el lenguaje de su elección y crea un cliente archivo de configuración de aplicación que puede usar para configurar su [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] objeto de cliente. Por ejemplo, si se crea un objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para invocar un `MyCalculatorService`, y se sabe que los metadatos de ese servicio están publicados en `http://computerName/MyCalculatorService/Service.svc?wsdl`, el siguiente ejemplo de código muestra cómo utilizar Svcutil.exe para obtener un archivo `ClientCode.vb` que contenga el contrato de servicios en código administrado.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Puede compilar este código de contrato en la aplicación cliente, o en otro ensamblado que la aplicación cliente puede utilizar para crear un objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Puede utilizar el archivo de configuración y configurar el objeto de cliente para conectarse correctamente con el servicio.  
  
 Para obtener un ejemplo de este proceso, consulte [Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Para obtener información más completa sobre los contratos, consulte [contratos](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Creación de un objeto de cliente de WCF  
 Un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente es un objeto local que representa un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio en un formulario que el cliente puede usar para comunicarse con el servicio remoto. Los tipos de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementan el contrato de servicio de destino, de modo que cuando cree uno y lo configure, puede usar el objeto cliente directamente para invocar operaciones de servicio. El [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ejecutar convierte de tiempo, el método llama a mensajes, los envía al servicio, realiza escuchas para la respuesta y devuelve esos valores para la [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] objeto de cliente como valores devueltos o `out` o `ref` parámetros.  
  
 También pueden utilizarse los objetos de canal de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para la conexión con los servicios y la utilización de los mismos. Para obtener más información, consulte [arquitectura de cliente de WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Creación de un nuevo objeto WCF  
 Para mostrar la utilización de una clase <xref:System.ServiceModel.ClientBase%601>, supongamos que el siguiente contrato de servicio simple se ha generado a partir de una aplicación de servicio.  
  
> [!NOTE]
>  Si utiliza Visual Studio para crear su [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente, los objetos se cargan automáticamente en el Examinador de objetos cuando se agrega una referencia de servicio a su proyecto.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Si no se utiliza Visual Studio, examine el código de contrato generado para encontrar el tipo que extiende <xref:System.ServiceModel.ClientBase%601> y la interfaz de contrato de servicio `ISampleService`. En este caso, ese tipo es similar al código siguiente:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Esta clase puede crearse como un objeto local, mediante uno de los constructores, configurarse y, a continuación, utilizarse para la conexión con un servicio del tipo `ISampleService`.  
  
 Se recomienda crear primero el objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], y, a continuación, utilizarlo y cerrarlo dentro de un único bloque try/catch. No debe utilizar el `using` instrucción (`Using` en Visual Basic) porque puede enmascarar excepciones en ciertos modos de error. Para obtener más información, consulte las secciones siguientes como [evitar problemas con la instrucción Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Contratos, enlaces y direcciones  
 Antes de poder crear un objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], este debe configurarse. En concreto, debe tener un servicio *extremo* a usar. Un punto de conexión es la combinación de un contrato de servicio, un enlace y una dirección. (Para obtener más información acerca de los extremos, vea [extremos: direcciones, enlaces y contratos](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) Normalmente, esta información se encuentra en la [ \<extremo >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) elemento en un archivo de configuración de aplicación de cliente, como el que la herramienta Svcutil.exe genera y se carga automáticamente cuando se crea el cliente objeto. Ambos tipos de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también tienen sobrecargas que permiten especificar esta información mediante programación.  
  
 Por ejemplo, un archivo de configuración generado para el `ISampleService` utilizado en los ejemplos anteriores, contiene la información de extremo siguiente.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Este archivo de configuración especifica un extremo de destino en el elemento `<client>`. Para obtener más información sobre el uso de varios puntos de conexión de destino, consulte el <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> constructores.  
  
## <a name="calling-operations"></a>Llamadas a operaciones  
 Una vez creado y configurado un objeto de cliente, cree un bloque try/catch, llame a las operaciones del mismo modo a como lo haría si el objeto fuese local, y cierre el objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Cuando la aplicación cliente llama a la primera operación, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] abre automáticamente el canal subyacente, que se cierra al reciclar el objeto. (De manera alternativa, también puede abrir y cerrar explícitamente el canal antes o después de llamar a otras operaciones).  
  
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
  
 Puede llamar a las operaciones mediante la creación de un objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y la llamada a sus métodos, como muestra el ejemplo de código siguiente. Tenga en cuenta que la apertura, llamada y cierre del objeto de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] tiene lugar en un bloque try/catch único. Para obtener más información, consulte [al tener acceso a los servicios mediante un cliente WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) y [evitar problemas con la instrucción Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Control de errores  
 Las excepciones pueden producirse en una aplicación cliente cuando se abre el canal de cliente subyacente (explícita o automáticamente mediante la llamada a una operación), se utiliza el cliente u objeto de canal para llamar a las operaciones, o se cierra el canal de cliente subyacente. Se recomienda como mínimo que las aplicaciones prevean administrar posibles <xref:System.TimeoutException?displayProperty=nameWithType> y las excepciones <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>, además de cualquier objeto <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> iniciado como resultado de los errores de SOAP devueltos por las operaciones. Los errores de SOAP especificados en el contrato de operación se elevan a las aplicaciones cliente como <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, donde el parámetro de tipo es el tipo de detalle del error de SOAP. Para obtener más información sobre el control de las condiciones de error en una aplicación cliente, consulte [enviar y recibir errores](../../../docs/framework/wcf/sending-and-receiving-faults.md). Para un ejemplo completo que muestre cómo controlar errores en un cliente, consulte [espera excepciones](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Configuración y protección de clientes.  
 La configuración de un cliente se inicia con la carga de información de extremo de destino necesaria para el cliente u objeto de canal, normalmente desde un archivo de configuración, aunque también puede cargarse esta información mediante programación utilizando los constructores y propiedades de cliente. No obstante, son necesarios pasos de configuración adicionales que habiliten cierto comportamiento del cliente y diferentes escenarios de seguridad.  
  
 Por ejemplo, los requisitos de seguridad para los contratos de servicios se declaran en la interfaz del contrato de servicio; si Svcutil.exe creó un archivo de configuración, ese archivo contiene, normalmente, un enlace capaz de admitir los requisitos de seguridad del servicio. En algunos casos, sin embargo, puede ser necesaria una mayor configuración de seguridad, como la configuración de credenciales de cliente. Para obtener información completa sobre la configuración de seguridad para [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] clientes, consulte [proteger clientes](../../../docs/framework/wcf/securing-clients.md).  
  
 Además, algunas modificaciones personalizadas se pueden habilitar en aplicaciones cliente, como comportamientos en tiempo de ejecución personalizados. Para obtener más información sobre cómo configurar un comportamiento de cliente personalizado, consulte [configurar comportamientos del cliente](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Creación de objetos de devolución de llamada para servicios dúplex.  
 Los servicios dúplex especifican un contrato de devolución de llamada que la aplicación cliente debe implementar para proporcionar un objeto de devolución de llamada, y que el servicio realice las llamadas según los requisitos del contrato. Aunque los objetos de devolución de llamada no son servicios completos (por ejemplo, no puede iniciar un canal con un objeto de devolución de llamada), en lo que respecta la implementación y la configuración pueden concebirse como un tipo de servicio.  
  
 Los clientes de servicios dúplex deben:  
  
-   Implementar una clase de contrato de devolución de llamada.  
  
-   Crear una instancia de la clase de implementación de contrato de devolución de llamada, y utilizarla para crear el objeto <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> que se pasa al constructor de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Invocar operaciones y controlar las devoluciones de llamada de la operación.  
  
 Los objetos de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] dúplex funcionan como sus homólogos no dúplex, salvo que exponen la funcionalidad necesaria para admitir las devoluciones de llamada, incluida la configuración del servicio de devolución de llamada.  
  
 Por ejemplo, pueden controlarse distintos aspectos del comportamiento del tiempo de ejecución del objeto de devolución de llamada mediante las propiedades del atributo <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>, en la clase de devolución de llamada. Otro ejemplo es el uso de la clase <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> para habilitar el retorno de información de excepción a los servicios que llaman al objeto de devolución de llamada. Para obtener más información, consulte [servicios dúplex](../../../docs/framework/wcf/feature-details/duplex-services.md). Para obtener un ejemplo completo, vea [dúplex](../../../docs/framework/wcf/samples/duplex.md).  
  
 En los equipos de Windows XP que ejecutan Internet Information Services (IIS) 5.1, los clientes dúplex deben especificar una dirección base de cliente utilizando la clase <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, o se iniciará una excepción. En el ejemplo de código siguiente se muestra cómo realizar esta especificación en el código.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 El código siguiente muestra cómo realizar esta especificación en un archivo de configuración  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Llamada a servicios de manera asincrónica.  
 La manera cómo se realizan las llamadas a las operaciones depende del desarrollador cliente. La razón es que los mensajes que constituyen una operación pueden asignarse a métodos sincrónicos o asincrónicos cuando se expresan en código administrado. Por consiguiente, si desea crear un cliente que llama a las operaciones de manera asincrónica, puede utilizar Svcutil.exe para generar código de cliente asincrónico mediante la opción `/async`. Para obtener más información, consulte [Cómo: llamar a las operaciones de servicio de forma asincrónica](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Llamada a los servicios mediante canales de cliente WCF.  
 Los tipos de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] extienden <xref:System.ServiceModel.ClientBase%601>, que, a su vez, deriva de la interfaz <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> para exponer el sistema del canal subyacente. Puede invocar los servicios utilizando el contrato de servicios de destino con la clase <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Para obtener más información, consulte [arquitectura de cliente de WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
