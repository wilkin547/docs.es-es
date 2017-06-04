---
title: "Sesi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Sesiones"
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# Sesi&#243;n
El ejemplo de sesión muestra cómo implementar un contrato que requiere una sesión.Una sesión proporciona el contexto para realizar varias operaciones.Esto permite a un servicio asociar el estado a una sesión determinada, de manera que las operaciones posteriores puedan usar el estado de una operación anterior.Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa un servicio de calculadora.El contrato `ICalculator` se ha modificado para permitir que se realice un conjunto de operaciones aritméticas, mientras se mantiene un resultado en ejecución.El contrato `ICalculatorSession` define esta funcionalidad.El servicio mantiene el estado para un cliente ya que se llama a varias operaciones de servicio para realizar un cálculo.El cliente puede recuperar el resultado actual llamando a `Result()` y borrar el resultado para ponerlo a cero llamando a `Clear()`.  
  
 En este ejemplo, el cliente es una aplicación de consola \(.exe\) e Internet Information Services \(IIS\) hospeda al servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Establecer <xref:System.ServiceModel.SessionMode> del contrato en `Required` garantiza que cuando el contrato se expone en un enlace en concreto, el enlace admita las sesiones.Si el enlace no admite sesiones, se producirá una excepción.La interfaz `ICalculatorSession` se define de tal forma que se pueda llamar a más operaciones, que modifica un resultado en ejecución, tal y como se muestra en el siguiente código de ejemplo.  
  
```  
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
  
 El servicio utiliza <xref:System.ServiceModel.InstanceContextMode> de <xref:System.ServiceModel.InstanceContextMode> para enlazar un contexto de instancia de servicio determinado para cada sesión de entrada.Esto permite al servicio mantener el resultado en ejecución para cada sesión en una variable del miembro local.  
  
```  
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
  
 Al ejecutar el ejemplo, el cliente realiza varias solicitudes al servidor y solicita el resultado, que se mostrará a continuación en la ventana de la consola del cliente.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## Vea también