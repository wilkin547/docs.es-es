---
title: Extensión de control a control de errores y creación de informes
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: 68f3381e8db9d7c0222720dda335b47e30f57ac7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183680"
---
# <a name="extending-control-over-error-handling-and-reporting"></a>Extensión de control a control de errores y creación de informes
En este ejemplo se muestra cómo ampliar el control sobre el control de <xref:System.ServiceModel.Dispatcher.IErrorHandler> errores y los informes de errores en un servicio de Windows Communication Foundation (WCF) mediante la interfaz. El ejemplo se basa en la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) con código adicional agregado al servicio para controlar los errores. El cliente fuerza varias condiciones de error. El servicio intercepta los errores y los registra en un archivo.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Los servicios pueden interceptar los errores, realizar el procesamiento y afectar la forma en que se crean informes sobre errores usando la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler>. La interfaz tiene dos métodos que pueden implementarse: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> y <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>. El método <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> le permite agregar, modificar o suprimir un mensaje de error que se genera como respuesta a una excepción. El método <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> permite que tenga lugar el procesamiento de errores en el caso de un error y controla si se puede ejecutar el control de errores adicional.  
  
 En este ejemplo, el tipo `CalculatorErrorHandler` implementa la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler>. En el campo   
  
 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>, `CalculatorErrorHandler` escribe un registro del error en un archivo de texto Error.txt en c:\logs. Observe que el ejemplo registra el error y no lo suprime, permitiendo que se cree un informe en el cliente.  
  
```csharp
public class CalculatorErrorHandler : IErrorHandler
{
    // Provide a fault. The Message fault parameter can be replaced, or set to
    // null to suppress reporting a fault.

    public void ProvideFault(Exception error, MessageVersion version, ref Message fault)
    {
    }

    // HandleError. Log an error, then allow the error to be handled as usual.
    // Return true if the error is considered as already handled

    public bool HandleError(Exception error)
    {
        using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))
        {
            if (error != null)
            {
                tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);
            }
            tw.Close();
        }
        return true;
    }
}  
```  
  
 `ErrorBehaviorAttribute` existe como mecanismo para registrar un controlador de errores con un servicio. Este atributo toma un parámetro de tipo único. Ese tipo debería implementar la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> y tener un constructor público y vacío. El atributo crea instancias de una instancia de ese tipo de controlador de errores y lo instala en el servicio. Hace esto implementando la interfaz <xref:System.ServiceModel.Description.IServiceBehavior> y utilizando el método <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> para agregar instancias del controlador de errores al servicio.  
  
```csharp
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }
    }  
}  
```  
  
 El ejemplo implementa un servicio de calculadora. El cliente hace que se produzcan dos errores de manera deliberada en el servicio proporcionando parámetros con valores no válidos. `CalculatorErrorHandler` utiliza la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> para registrar los errores en un archivo local y, a continuación, informar de ellos al cliente. El cliente fuerza una división por cero y una condición de argumento fuera de intervalo.  
  
```csharp
try
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Ve la división por cero y las condiciones del argumento fuera del intervalo que aparecen en el informe como errores. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 El archivo c:\logs\errors.txt contiene la información registrada sobre los errores por el servicio. Tenga en cuenta que para que el servicio escriba en el directorio debe asegurarse de que el proceso en el que se ejecuta el servicio (normalmente ASP.NET o Servicio de red) tiene permiso para escribir en el directorio.  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Para compilar la solución, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .  
  
3. Asegúrese de que ha creado el directorio c:\logs para el archivo error.txt. O modifique el nombre de archivo utilizado en `CalculatorErrorHandler.HandleError`.  
  
4. Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
