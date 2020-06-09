---
title: Creación de instancias
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, instancing sample
- Instancing Sample [Windows Communication Foundation]
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
ms.openlocfilehash: 1cfaa0db5b81858b733343f17cae71e5815ef60b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596636"
---
# <a name="instancing"></a>Creación de instancias
El ejemplo de la creación de instancias muestra el valor de comportamiento de creación de instancias, que controla cómo las instancias de una clase de servicio se crean en respuesta a las solicitudes de cliente. El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio. Este ejemplo define un nuevo contrato, `ICalculatorInstance`, que se hereda de `ICalculator`. El contrato especificado por `ICalculatorInstance` proporciona tres operaciones adicionales para inspeccionar el estado de la instancia del servicio. Modificando el valor de la creación de instancias, puede observar el cambio en el comportamiento ejecutando el cliente.  
  
 En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Los siguientes modos de creación de instancias están disponibles:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: Se crea un Nuevo servicio para cada solicitud de cliente.  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: Se crea una nueva instancia para cada nueva sesión del cliente y se mantiene durante el tiempo que dure esa sesión (esto requiere un enlace que admita una sesión).  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: Una única instancia de la clase del servicio administra todas las solicitudes de cliente durante la vida de la aplicación  
  
 La clase de servicio especifica el comportamiento de la creación de instancias con el atributo `[ServiceBehavior(InstanceContextMode=<setting>)]` como se muestra en el ejemplo de código que sigue. Cambiando las líneas que se marcan con comentarios, se puede observar el comportamiento de cada uno de los modos de la instancia. Recuerde recompilar el servicio después de cambiar el modo de la creación de instancias. No hay ninguna configuración relacionada con la creación de instancias para especificar en el cliente.  
  
```csharp
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Se muestra el modo de la instancia en el cual el servicio se está ejecutando. Tras cada operación, se muestran el Id. de la instancia y el recuento de la operación, para reflejar el comportamiento del modo de la creación de instancias. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
