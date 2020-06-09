---
title: Hospedaje de IIS utilizando código en línea
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 47d056e35b92654c8e47647c7273c5d69b37bd97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594652"
---
# <a name="iis-hosting-using-inline-code"></a>Hospedaje de IIS utilizando código en línea

Este ejemplo muestra cómo implementar un servicio hospedado por Internet Information Services (IIS), donde el código de servicio está contenido en línea en un archivo .svc y se compila a petición. El código de servicio también se puede implementar directamente en los archivos de código de origen situado en el directorio \App_Code de la aplicación o compilado en un ensamblado implementado en \bin. Este ejemplo no muestra estas técnicas.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

El ejemplo muestra un servicio típico que implementa un contrato que define un modelo de comunicación solicitud-respuesta. El servicio se hospeda en IIS y el código de servicio se contiene completamente en el archivo Service.svc. El primer mensaje enviado al servicio permite que éste se active en el host y se compile a petición. No es necesario realizar una compilación previa. El servicio implementa un contrato `ICalculator` tal y como se define en el código siguiente:

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

La implementación del servicio calcula y devuelve el resultado adecuado.

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

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

3. Una vez compilada la solución, ejecute setup. bat para configurar la aplicación ServiceModelSamples en IIS 7,0. El directorio ServiceModelSamples debería aparecer ahora como una aplicación de IIS 7,0.

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md). Para obtener un ejemplo sobre cómo crear una aplicación cliente que pueda llamar a este servicio, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).

## <a name="see-also"></a>Vea también

- [Ejemplos de hospedaje y persistencia de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
