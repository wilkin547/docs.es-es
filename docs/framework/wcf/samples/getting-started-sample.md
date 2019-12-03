---
title: Ejemplo de introducción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: 3282daff166a8fe56841a41bfe8bd9dd69f9d4c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716943"
---
# <a name="getting-started-sample"></a>Ejemplo de introducción

En el ejemplo Introducción se muestra cómo implementar un servicio típico y un cliente típico mediante Windows Communication Foundation (WCF). Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

El servicio describe las operaciones que realiza en un contrato de servicios que expone públicamente como metadatos. El servicio también contiene el código para implementar las operaciones.

El cliente contiene una definición del contrato de servicios y una clase de proxy para tener acceso al servicio. El código proxy se genera a partir de los metadatos del servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).

En [!INCLUDE[wv](../../../../includes/wv-md.md)], el servicio se hospeda en el Servicio de Activación de Windows (WAS). Internet Information Services (IIS) y ASP.NET hospedan [!INCLUDE[wxp](../../../../includes/wxp-md.md)] y [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Hospedar un servicio en IIS o WAS permite activar el servicio automáticamente cuando se tiene acceso por primera vez.

> [!NOTE]
> Si prefiere empezar a trabajar con un ejemplo que hospeda el servicio en una aplicación de consola en lugar de en IIS, consulte el ejemplo de [host propio](../../../../docs/framework/wcf/samples/self-host.md) .

El servicio y cliente especifican los detalles de acceso en valores de archivo de configuración, los cuales proporciona la flexibilidad en el momento de la implementación. Esto incluye una definición de punto de conexión que especifica una dirección, un enlace y un contrato. El enlace especifica el transporte y los detalles de seguridad sobre cómo se tiene acceso al servicio.

El servicio configura un comportamiento de tiempo de ejecución para publicar sus metadatos.

El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. El cliente realiza solicitudes a una operación matemática concreta y el servicio responde con el resultado. El servicio implementa un contrato `ICalculator` que se define en el código siguiente.

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
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
```

La implementación del servicio calcula y devuelve el resultado adecuado, tal y como se muestra en el siguiente ejemplo de código.

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

El servicio expone un punto de conexión para comunicarse con el servicio, que se define utilizando un archivo de configuración (Web.config), como se muestra en la configuración de ejemplo siguiente.

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

El servicio expone el punto de conexión en la dirección base proporcionada por el host IIS o WAS. El enlace se configura con un <xref:System.ServiceModel.WSHttpBinding>estándar, que proporciona comunicación del HTTP y protocolos estándar del servicio Web para direccionar y seguridad. El contrato es el `ICalculator` implementado por el servicio.

Tal y como se ha configurado, se puede tener acceso al servicio en `http://localhost/servicemodelsamples/service.svc` un cliente en el mismo equipo. Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.

El marco no expone ningún metadato de forma predeterminada. Como tal, el servicio activa el <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y expone un punto de conexión de intercambio de metadatos (MEX) en `http://localhost/servicemodelsamples/service.svc/mex`. La siguiente configuración lo muestra.

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

El cliente se comunica utilizando un tipo de contrato determinado mediante una clase de cliente generada por la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Este cliente generado se encuentra en el archivo generatedClient.cs o generatedClient.vb. Esta utilidad recupera los metadatos para un servicio determinado y genera un cliente para el uso por la aplicación del cliente para comunicarse, utilizando un tipo de contrato determinado. El servicio hospedado debe estar disponible para generar el código de cliente, porque el servicio se utiliza para recuperar los metadatos actualizados.

 Ejecute el comando siguiente desde un símbolo del sistema SDK en el directorio cliente para generar el proxy especificado:

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

Para generar el cliente en el tipo Visual Basic el siguiente símbolo del sistema de SDK:

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

Al utilizar el cliente generado, el cliente puede tener acceso a un punto de conexión de servicio determinado configurando la dirección adecuada y el enlace. Como el servicio, el cliente utiliza un archivo de configuración (App.config) para especificar el punto de conexión con el que desea comunicarse. La configuración del extremo del cliente está compuesta por una dirección absoluta para el extremo del servicio, el enlace y el contrato, tal y como se muestra en el siguiente ejemplo.

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

La implementación del cliente crea instancias de cliente y utiliza la interfaz especificada para empezar a comunicarse con el servicio, como se muestra en el código de ejemplo siguiente.

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

El ejemplo de la Introducción muestra la manera estándar de crear un servicio y un cliente. La otra compilación [básica](../../../../docs/framework/wcf/samples/basic-sample.md) sobre este ejemplo para mostrar características específicas del producto.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="see-also"></a>Vea también

- [Cómo hospedar un servicio WCF en una aplicación administrada](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
