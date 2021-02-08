---
description: 'Más información acerca de: cliente ASMX con un servicio WCF'
title: Cliente ASMX con un servicio WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: b9f561f6651c591556f821478c4c4bfd7d7da23d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778924"
---
# <a name="asmx-client-with-a-wcf-service"></a>Cliente ASMX con un servicio WCF

Este ejemplo muestra cómo crear un servicio mediante Windows Communication Foundation (WCF) y, a continuación, obtener acceso al servicio desde un cliente que no sea de WCF, como un cliente ASMX.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS). El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`) define el contrato. El cliente ASMX realiza solicitudes sincrónicas a una operación matemática y el servicio responde con el resultado.

El servicio implementa un contrato `ICalculator` tal y como se define en el código siguiente.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
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

<xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer> asignan los tipos CLR a una representación XML. <xref:System.Runtime.Serialization.DataContractSerializer> interpreta algunas representaciones XML de manera diferente a XmlSerializer. Los generadores de proxy que no son de WCF, como Wsdl.exe, generan una interfaz más utilizable cuando se usa XmlSerializer. <xref:System.ServiceModel.XmlSerializerFormatAttribute>Se aplica a la `ICalculator` interfaz para asegurarse de que se utiliza XmlSerializer para asignar tipos CLR a XML. La implementación del servicio calcula y devuelve el resultado adecuado.

El servicio expone un extremo único para comunicarse con el servicio, que se define utilizando el archivo de configuración (Web.config). El punto de conexión está compuesto por una dirección, un enlace y un contrato. El servicio expone el extremo en la dirección base proporcionada por el host de Internet Information Services (IIS). El atributo `binding` está definido en basicHttpBinding, que proporciona las comunicaciones HTTP usando SOAP 1.1, que es conforme a WS-I BasicProfile 1.1, tal y como se muestra en la configuración del ejemplo siguiente.

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

El cliente ASMX se comunica con el servicio WCF mediante un proxy con tipo generado por la utilidad de lenguaje de descripción de servicios web (WSDL) (Wsdl.exe). El proxy con tipo se encuentra en el archivo generatedClient.cs. La utilidad WSDL recupera los metadatos para el servicio especificado y genera un proxy con tipo para que un cliente lo utilice para comunicarse. De forma predeterminada, el marco no expone ningún metadato. Para exponer los metadatos necesarios para generar el proxy, debe agregar [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) y establecer su `httpGetEnabled` atributo en `True` tal y como se muestra en la configuración siguiente.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

Ejecute el comando siguiente desde un símbolo del sistema en el directorio del cliente para generar el proxy especificado.

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

Al utilizar el proxy con tipo generado, el cliente puede tener acceso a un punto de conexión de servicio determinado configurando la dirección adecuada. El cliente utiliza un archivo de configuración (App.config) para especificar el punto de conexión con el que comunicarse.

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

La implementación del cliente construye una instancia del proxy con tipo para comenzar la comunicación con el servicio.

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
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

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

> [!NOTE]
> Para obtener más información sobre cómo pasar y devolver tipos de datos complejos, consulte [enlace de datos en un cliente de Windows Forms](data-binding-in-a-windows-forms-client.md), [enlace de datos en un cliente Windows Presentation Foundation](data-binding-in-a-wpf-client.md)y [enlace de datos en un cliente de ASP.net](data-binding-in-an-aspnet-client.md)

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
