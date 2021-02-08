---
description: 'Más información acerca de: sesión'
title: Sesión
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: ba8d2d44d0be22243bd1562f9bd499d68a1112af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793030"
---
# <a name="session"></a>Sesión

El ejemplo de sesión muestra cómo implementar un contrato que requiere una sesión. Una sesión proporciona el contexto para realizar varias operaciones. Esto permite a un servicio asociar el estado a una sesión determinada, de manera que las operaciones posteriores puedan usar el estado de una operación anterior. Este ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa un servicio de calculadora. El contrato `ICalculator` se ha modificado para permitir que se realice un conjunto de operaciones aritméticas, mientras se mantiene un resultado en ejecución. El contrato `ICalculatorSession` define esta funcionalidad. El servicio mantiene el estado para un cliente ya que se llama a varias operaciones de servicio para realizar un cálculo. El cliente puede recuperar el resultado actual llamando a `Result()` y borrar el resultado para ponerlo a cero llamando a `Clear()`.  
  
 En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Establecer <xref:System.ServiceModel.SessionMode> del contrato en `Required` garantiza que cuando el contrato se expone en un enlace en concreto, el enlace admita las sesiones. Si el enlace no admite sesiones, se producirá una excepción. La interfaz `ICalculatorSession` se define de tal forma que se pueda llamar a más operaciones, que modifica un resultado en ejecución, tal y como se muestra en el siguiente código de ejemplo.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 El servicio utiliza <xref:System.ServiceModel.InstanceContextMode> de <xref:System.ServiceModel.InstanceContextMode.PerSession> para enlazar un contexto de instancia de servicio determinado para cada sesión de entrada. Esto permite al servicio mantener el resultado en ejecución para cada sesión en una variable del miembro local.  
  
```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 Al ejecutar el ejemplo, el cliente realiza varias solicitudes al servidor y solicita el resultado, que se mostrará a continuación en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
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
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
