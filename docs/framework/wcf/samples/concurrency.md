---
title: "Simultaneidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ejemplo de simultaneidad [Windows Communication Foundation]"
  - "comportamientos del servicio, ejemplo de simultaneidad"
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
caps.latest.revision: 32
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 32
---
# Simultaneidad
El ejemplo de la Simultaneidad muestra cómo utilizar <xref:System.ServiceModel.ServiceBehaviorAttribute> con la enumeración <xref:System.ServiceModel.ConcurrencyMode>, que controla si una instancia de un servicio procesa secuencialmente o simultáneamente los mensajes.  El ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa el contrato de servicio `ICalculator`.  Este ejemplo define un nuevo contrato, `ICalculatorConcurrency`, que hereda de `ICalculator`, proporcionando dos operaciones adicionales para inspeccionar el estado de la simultaneidad del servicio.  Modificando el valor de simultaneidad, puede observar el cambio en el comportamiento ejecutando el cliente.  
  
 En este ejemplo, el cliente es una aplicación de consola \(.exe\) y los Servicios de Internet Information Server \(IIS\) hospedan el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Hay tres modos de simultaneidad disponibles:  
  
-   `Single`: Cada instancia del servicio procesa a la vez un mensaje.  Éste es el modo de simultaneidad predeterminado.  
  
-   `Multiple`: Cada instancia del servicio procesa simultáneamente varios mensajes.  La implementación del servicio debe ser segura para los subprocesos para utilizar este modo de simultaneidad.  
  
-   `Reentrant`: cada instancia de servicio procesa a la vez un mensaje, pero acepta llamadas reentrantes.  El servicio solo acepta estas llamadas cuando está llamando.  El Reentrante se muestra en el ejemplo [ConcurrencyMode.  Reentrante](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md).  
  
 El uso de simultaneidad se relaciona con el modo de creación de instancias.  Para crear instancias<xref:System.ServiceModel.InstanceContextMode>, la simultaneidad no es pertinente, porque una nueva instancia del servicio procesa cada mensaje.  Para crear instancias<xref:System.ServiceModel.InstanceContextMode>, o<xref:System.ServiceModel.ConcurrencyMode> o la simultaneidad <xref:System.ServiceModel.ConcurrencyMode> es pertinente, dependiendo de si la instancia única procesa secuencialmente o simultáneamente los mensajes.  Para crear instancias<xref:System.ServiceModel.InstanceContextMode>, cualquiera de los modos de la simultaneidad puede ser pertinente.  
  
 La clase de servicio especifica el comportamiento de la simultaneidad con el atributo `[ServiceBehavior(ConcurrencyMode=<setting>)]` como se muestra en el ejemplo de código que sigue.  Cambiando las líneas marcadas con comentarios, se puede experimentar con `Single` y con los modos de simultaneidad `Multiple`.  Recuerde recompilar el servicio después de cambiar el modo de la simultaneidad.  
  
```  
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {     
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {     
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 El ejemplo utiliza la simultaneidad <xref:System.ServiceModel.ConcurrencyMode> con <xref:System.ServiceModel.InstanceContextMode> que crea instancias de forma predeterminada.  El código de cliente se ha modificado para utilizar un proxy asincrónico.  Esto permite al cliente realizar varias llamadas al servicio sin esperar por una respuesta entre cada llamada.  Puede observar la diferencia en el comportamiento del modo de simultaneidad de servicio.  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.  Se muestra el modo de la simultaneidad en el que el servicio se está ejecutando, se llama a cada operación y, a continuación, se muestra el recuento de la operación.  Observe que cuando el modo de la simultaneidad es `Multiple`, los resultados se devuelven en un orden diferente a como se llamaron, porque el servicio procesa simultáneamente varios mensajes.  Cambiando el modo de simultaneidad a `Single`, los resultados se devuelven en el orden en que se denominaron, porque el servicio procesa secuencialmente cada mensaje.  Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
### Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar el procedimiento de [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Si utiliza Svcutil.exe para generar el cliente del proxy, asegurarse de que incluye la opción `/async`.  
  
3.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
  
## Vea también