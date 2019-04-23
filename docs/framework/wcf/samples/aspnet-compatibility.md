---
title: Compatibilidad de ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 01381dc579f5ae3eadd2f913a0e09d7d259794a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304228"
---
# <a name="aspnet-compatibility"></a>Compatibilidad de ASP.NET
Este ejemplo muestra cómo habilitar el modo de compatibilidad de ASP.NET en Windows Communication Foundation (WCF). Servicios que se ejecutan en la compatibilidad de ASP.NET modo participan totalmente en la canalización de aplicación de ASP.NET y puede hacer usan de las características ASP.NET como archivo/autorización de URL, estado de sesión y el <xref:System.Web.HttpContext> clase. La <xref:System.Web.HttpContext> clase permite el acceso a las cookies, sesiones y otras características de ASP.NET. Este modo requiere que los enlaces utilicen el transporte HTTP y el propio servicio se debe hospedar en IIS.  
  
 En este ejemplo, el cliente es una aplicación de consola (un ejecutable) e Internet Information Servers (IIS) hospeda el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
En este ejemplo se requiere un grupo de aplicaciones de [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] para ejecutarse. Para crear un nuevo grupo de aplicaciones o modificar el grupo de aplicaciones predeterminado, siga estos pasos.  

1. Abra **Panel de Control**.  Abra el **herramientas administrativas** subprograma en el **sistema y seguridad** encabezado. Abra el **Internet Information Services (IIS) Manager** applet.  

2. Expanda la vista de árbol en el **conexiones** panel. Seleccione el **grupos de aplicaciones** nodo.  

3. Para establecer el grupo de aplicaciones predeterminado a usar [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (lo que puede producir problemas de incompatibilidad con los sitios existentes), haga clic en el **DefaultAppPool** de elemento de lista y seleccione **configuración básica...** . Establecer el **.Net Framework versión** desplegable para **.Net Framework v4.0.30128** (o posterior).  

4. Para crear un nuevo grupo de aplicaciones que usa [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (para conservar la compatibilidad con otras aplicaciones), haga clic en el **grupos de aplicaciones** nodo y seleccione **Agregar grupo de aplicaciones...** . Nombre del nuevo grupo de aplicaciones y establecer el **.Net Framework versión** desplegable para **.Net Framework v4.0.30128** (o posterior). Después de ejecutar el programa de instalación de pasos a continuación, haga clic en el **ServiceModelSamples** aplicación y seleccione **administrar aplicación**, **configuración avanzada...** . Establecer el **AppPool** al nuevo grupo de aplicaciones.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa un servicio de calculadora. El contrato `ICalculator` se ha modificado como contrato`ICalculatorSession` para permitir realizar un conjunto de operaciones, manteniendo un resultado en ejecución.  
  
```csharp  
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
  
 El servicio mantiene el estado, utilizando la característica, para cada cliente ya que se llama a varias operaciones de servicio para realizar un cálculo. El cliente puede recuperar el resultado actual llamando a `Result` y borrar el resultado para ponerlo a cero llamando a `Clear`.  
  
 El servicio utiliza la sesión de ASP.NET para almacenar el resultado de cada sesión de cliente. Esto permite al servicio mantener el resultado en ejecución para cada cliente por varias llamadas al servicio.  
  
> [!NOTE]
> Estado de sesión ASP.NET y las sesiones WCF son cosas muy diferentes. Consulte [sesión](../../../../docs/framework/wcf/samples/session.md) para obtener más información sobre las sesiones WCF.
  
 El servicio tiene una dependencia íntima en estado de sesión ASP.NET y requiere el modo de compatibilidad ASP.NET funcione correctamente. Estos requisitos se expresan mediante declaración aplicando el atributo `AspNetCompatibilityRequirements`.  
  
```csharp  
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
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. El directorio ServiceModelSamples debería aparecer ahora como una aplicación de [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de persistencia y el hospedaje de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)
