---
title: Unidireccional
ms.date: 03/30/2017
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
ms.openlocfilehash: 7732b63cccb98ac54d99a0430dbaf0c8abfdaaa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245047"
---
# <a name="one-way"></a>Unidireccional

Este ejemplo muestra un contacto del servicio con operaciones de servicio unidireccionales. El cliente no espera a que se completen las operaciones de servicio como en el caso de las operaciones de servicio bidireccionales. Este ejemplo se basa en el [Introducción](getting-started-sample.md) y utiliza el `wsHttpBinding` enlace. El servicio en este ejemplo es una aplicación de consola autohospedada que le permite observar el servicio que recibe y procesa las solicitudes. El cliente es también una aplicación de consola.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Para crear un contrato de servicio unidireccional, defina su contrato de servicio, aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación y establezca <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true`, tal y como se muestra en el código de ejemplo siguiente:  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 Para mostrar que el cliente no espera a que las operaciones de servicio se completen, el código de servicio en este ejemplo implementa un retraso de cinco segundos, tal y como se muestra en el código de ejemplo siguiente:  
  
```csharp
// This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 Cuando el cliente llama al servicio, la llamada se devuelve sin esperar a que la operación de servicio se complete.  
  
 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione ENTRAR en cada ventana de la consola para cerrar el servicio y el cliente.  
  
 El cliente finaliza delante del servicio, mostrando que un cliente no espera a que las operaciones de servicio unidireccional se completen. El resultado del cliente es el siguiente:  
  
```console  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 Se muestra el siguiente resultado del servicio:  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
> HTTP es, por definición, un protocolo de solicitud/respuesta; cuando se realiza una solicitud, se devuelve una respuesta. Esto es verdad incluso para una operación de servicio unidireccional que se expone sobre HTTP. Cuando se llama a la operación, el servicio devuelve un código de estado HTTP de 202 antes de que se ejecute la operación de servicio. Este código de estado significa que se ha aceptado el procesamiento de la solicitud, pero no se ha completado aún. El cliente que llamó a la operación se bloquea hasta que recibe la respuesta 202 del servicio. Esto puede producir comportamientos inesperados cuando se envían mensajes unidireccionales usando un enlace que se configura para usar sesiones. El enlace `wsHttpBinding` que se usa en este ejemplo se configura para utilizar sesiones de forma predeterminada a fin de establecer un contexto de seguridad. De forma predeterminada, se garantiza que los mensajes en una sesión lleguen en el orden en el que se enviaron. Debido a esto, cuando se envía el segundo mensaje en una sesión, no se procesa hasta que se haya procesado el primero. El resultado es que el cliente no recibe la respuesta 202 para un mensaje hasta que el procesamiento del mensaje anterior se haya completado. Parece, por tanto, que el cliente se bloquea en cada llamada de operación subsiguiente. Para evitar este comportamiento, este ejemplo configura el tiempo de ejecución para enviar mensajes a la vez a distintas instancias para el procesamiento. El ejemplo establece <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> en `PerCall` para que otra instancia diferente pueda procesar cada mensaje. <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en `Multiple` para permitir que más de un subproceso envíe mensajes al mismo tiempo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!NOTE]
> Ejecute el servicio antes de ejecutar el cliente y ciérrelo antes de cerrar el servicio. Esto evita una excepción del cliente cuando el cliente no puede cerrar la sesión de seguridad correctamente porque se haya cerrado el servicio.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
