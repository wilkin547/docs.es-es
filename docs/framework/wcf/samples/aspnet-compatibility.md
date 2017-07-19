---
title: "Compatibilidad de ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Compatibilidad de ASP.NET
Este ejemplo muestra cómo habilitar el modo de compatibilidad [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  Los servicios que se ejecutan en modo de compatibilidad [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] participan totalmente en el conductor de aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y pueden utilizar características [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] como archivo\/autorización de URL, estado de sesión y la clase <xref:System.Web.HttpContext>.  La clase <xref:System.Web.HttpContext> permite el acceso a las cookies, sesiones y otras características [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  Este modo requiere que los enlaces utilicen el transporte HTTP y el propio servicio se debe hospedar en IIS.  
  
 En este ejemplo, el cliente es una aplicación de consola \(un ejecutable\) e Internet Information Servers \(IIS\) hospeda el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!NOTE]
>  En este ejemplo se requiere un grupo de aplicaciones de [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] para ejecutarse.  Para crear un nuevo grupo de aplicaciones o modificar el grupo de aplicaciones predeterminado, siga estos pasos.  
>   
>  1.  Abra el **Panel de control**.  Abra el applet **Herramientas administrativas** bajo el encabezado **Sistema y seguridad**.  Abra el applet **Administrador de Internet Information Services \(IIS\)**.  
> 2.  Expanda la vista de árbol en el panel **Conexiones**.  Seleccione el nodo **Grupos de aplicaciones**.  
> 3.  Para establecer que el grupo de aplicaciones predeterminado use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] \(lo que puede producir problemas de incompatibilidad con los sitios existentes\), haga clic con el botón secundario en el elemento de la lista **DefaultAppPool** y seleccione **Configuración básica**.  Establezca el menú desplegable **Versión de .NET Framework** en **.Net Framework v4.0.30128** \(o posterior\).  
> 4.  Para crear un nuevo grupo de aplicaciones que use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] \(para conservar la compatibilidad con las demás aplicaciones\), haga clic con el botón secundario en el nodo **Grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.  Asigne un nombre al nuevo grupo de aplicaciones y establezca el menú desplegable **Versión de .NET Framework** en **.Net Framework v4.0.30128** \(o posterior\).  Después de ejecutar los pasos de instalación siguientes, haga clic con el botón secundario en la aplicación **ServiceModelSamples** y seleccione **Aplicación de administración** y en **Configuración avanzada**.  Establezca el **Grupo de aplicaciones** en el nuevo grupo de aplicaciones.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa un servicio de calculadora.  El contrato `ICalculator` se ha modificado como contrato`ICalculatorSession` para permitir realizar un conjunto de operaciones, manteniendo un resultado en ejecución.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
  
```  
  
 El servicio mantiene el estado, utilizando la característica, para cada cliente ya que se llama a varias operaciones de servicio para realizar un cálculo.  El cliente puede recuperar el resultado actual llamando a `Result` y borrar el resultado para ponerlo a cero llamando a `Clear`.  
  
 El servicio utiliza la sesión [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] para almacenar el resultado para cada sesión.  Esto permite al servicio mantener el resultado en ejecución para cada cliente por varias llamadas al servicio.  
  
> [!NOTE]
>  El estado de sesión [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y sesiones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son cosas muy diferentes.  Vea el [Sesión](../../../../docs/framework/wcf/samples/session.md) para más detalles sobre las sesiones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 El servicio tiene una dependencia íntima en estado de sesión [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y exige al modo de compatibilidad [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que funcione correctamente.  Estos requisitos se expresan mediante declaración aplicando el atributo `AspNetCompatibilityRequirements`.  
  
```  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.  Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
  
```  
  
### Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  El directorio ServiceModelSamples debería aparecer ahora como una aplicación de [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también  
 [Ejemplos de Hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)