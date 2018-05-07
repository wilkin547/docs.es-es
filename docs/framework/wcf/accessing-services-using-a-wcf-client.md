---
title: Acceso a los servicios mediante un cliente WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: d29483995a1fbf7a8c9918db0c3b65f7deac1e44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-services-using-a-wcf-client"></a>Acceso a los servicios mediante un cliente WCF
Después de crear un servicio, el paso siguiente es crear un cliente proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Una aplicación de cliente usa el cliente proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para comunicarse con el servicio. Las aplicaciones de cliente suelen importar los metadatos de un servicio para generar el código de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que se puede usar para invocar el servicio.  
  
 Los pasos básicos para crear un cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] son los siguientes:  
  
1.  Compilar el código del servicio.  
  
2.  Genere el proxy de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
3.  Cree una instancia del proxy de cliente de WCF.  
  
 El proxy de cliente WCF puede generarse manualmente mediante el uso de Service Model Metadata Utility Tool (SvcUtil.exe) para obtener más información, vea [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). El proxy de cliente de WCF también se puede generar en Visual Studio mediante la característica Agregar referencia de servicio. Para generar el proxy de cliente de WCF usando cualquier método, el servicio debe estar en ejecución. Si el servicio se autohospeda, debe ejecutar el host. Si el servicio se hospeda en IIS/WAS no necesita hacer nada más.  
  
## <a name="servicemodel-metadata-utility-tool"></a>Herramienta de utilidad de metadatos ServiceModel  
 El [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) es una herramienta de línea de comandos para generar código de metadatos. A continuación se muestra un ejemplo del uso de un comando básico Svcutil.exe.  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 Como alternativa, puede usar Svcutil.exe con archivos de Lenguaje de descripción de servicios Web (WSDL) y de lenguaje de definición de esquemas XML (XSD) en el sistema de archivos.  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 El resultado es un archivo de código que contiene código de cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que la aplicación de cliente puede usar para invocar el servicio.  
  
 También puede usar la herramienta para generar archivos de configuración.  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 Si se proporciona solo uno nombre de archivo, ése será el nombre del archivo de salida. Si se proporcionan dos nombres de archivo, entonces el primer archivo es un archivo de configuración de entrada cuyo contenido está combinado con la configuración generada y que se escribe en el segundo archivo. Para obtener más información acerca de la configuración, consulte [configurar enlaces para servicios](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Las solicitudes de metadatos que no son seguras plantean ciertos riesgos, al igual que cualquier solicitud de una red no segura: si no está seguro de que el punto de conexión con el que se está comunicando es el que dice ser, es posible que la información que recupere sean metadatos de un servicio malintencionado.  
  
## <a name="add-service-reference-in-visual-studio"></a>Agregar referencia de servicio en Visual Studio  
 Con el servicio en ejecución, haga clic en el proyecto que contendrá el proxy de cliente WCF y seleccione **Agregar referencia de servicio**. En el **Agregar cuadro de diálogo de referencia de servicio** escriba la dirección URL para el servicio que desea llamar y haga clic en el **vaya** botón. El cuadro de diálogo mostrará una lista de servicios disponibles en la dirección especificada. Haga doble clic en el servicio para ver los contratos y operaciones disponibles, especifique un espacio de nombres para el código generado y haga clic en el **Aceptar** botón.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra un contrato de servicio creado para un servicio.  
  
```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```
  
```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```
  
 La herramienta de utilidad de metadatos de ServiceModel y Agregar referencia de servicio en Visual Studio genera la clase de cliente siguiente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. La clase adquiere de la clase <xref:System.ServiceModel.ClientBase%601> genérica e implementa la interfaz `ICalculator`. La herramienta también genera la interfaz (no se muestra aquí) `ICalculator`.  
  
```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```  
  
```vb  
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```
  
## <a name="using-the-wcf-client"></a>Uso del cliente WCF  
 Para usar el cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], cree una instancia del cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y, a continuación, llame a sus métodos, tal y como se muestra en el código siguiente.  
  
```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```
  
```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```
  
## <a name="debugging-exceptions-thrown-by-a-client"></a>Depuración de las excepciones iniciadas por un cliente  
 Muchas de las excepciones iniciadas por un cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] tienen su origen en una excepción del servicio. Estos son algunos ejemplos:  
  
-   <xref:System.Net.Sockets.SocketException>: el host remoto forzó el cierre de la conexión existente.  
  
-   <xref:System.ServiceModel.CommunicationException>: la conexión ha terminado de forma inesperada.  
  
-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: se anuló la conexión de socket. La causa puede ser un error en el procesamiento del mensaje, que se superó el tiempo de espera de recepción en el host remoto, o bien un problema de recursos de red subyacente.  
  
 Cuando se producen estos tipos de excepciones, la mejor manera de resolver el problema es activar el seguimiento en el lado del servicio y determinar qué excepción se produjo allí. Para obtener más información acerca del seguimiento, vea [seguimiento](../../../docs/framework/wcf/diagnostics/tracing/index.md) y [utilizando el seguimiento para solucionar problemas de la aplicación](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Acceso a los servicios con un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Llamada a operaciones de servicio de forma asincrónica](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)  
 [Acceso a los servicios con contratos unidireccionales y de solicitud-respuesta](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)  
 [Acceso a un servicio WSE 3.0](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)  
 [Información sobre códigos de cliente generado](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)  
 [Mejora del tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)  
 [Especificación del comportamiento de tiempo de ejecución del cliente](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [Configuración de los comportamientos del cliente](../../../docs/framework/wcf/configuring-client-behaviors.md)
