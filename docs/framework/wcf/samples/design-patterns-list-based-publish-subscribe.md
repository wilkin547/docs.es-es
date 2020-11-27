---
title: 'Modelos de diseño: suscripción-publicación basada en la lista'
ms.date: 03/30/2017
ms.assetid: f4257abc-12df-4736-a03b-0731becf0fd4
ms.openlocfilehash: 4e679980df8a720eb4aa22741bbdd067940c7723
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292680"
---
# <a name="design-patterns-list-based-publish-subscribe"></a>Modelos de diseño: suscripción-publicación basada en la lista

Este ejemplo muestra el patrón de Publish-Subscribe basado en lista implementado como un programa de Windows Communication Foundation (WCF).  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El modelo de diseño de Publish-Subscribe basado en lista se describe en la publicación Microsoft Patterns & Practices, [patrones de integración](/previous-versions/msp-n-p/ff647309(v=pandp.10)). El patrón suscripción-publicación pasa información a una colección de destinatarios que se han suscrito a un tema de la información. La suscripción-publicación basada en la lista mantiene una lista de suscriptores. Cuando hay información para compartir, se envía una copia a cada suscriptor en la lista. Este ejemplo muestra un patrón dinámico de suscripción-publicación basada en la lista, donde los clientes pueden suscribirse o cancelar su suscripción tan a menudo como sea necesario.  
  
 El ejemplo de suscripción-publicación basada en la lista está compuesto de un cliente, un servicio y un programa de origen de datos. Puede haber más de un cliente y más de un funcionamiento de programa de origen de datos. Los clientes se suscriben al servicio, reciben las notificaciones y cancelan su suscripción. Los programas de origen de datos envían información al servicio para a compartir con todos los suscriptores actuales.  
  
 En este ejemplo, el cliente y el origen de datos son los programas de consola (archivos .exe) y el servicio es una biblioteca (.dll) hospedada en IIS (Servicios de Internet Information Server) (IIS). El cliente y la actividad de origen de datos están visibles en el escritorio.  
  
 El servicio utiliza la comunicación dúplex. El contrato de servicios `ISampleContract` se empareja a con un contrato de devolución de llamada `ISampleClientCallback`. El servicio implementa la operaciones del servicio Suscripción y Cancelación, que los clientes utilizan para unirse a la lista de suscriptores o para dejar la misma. El servicio también implementa la operación de servicio `PublishPriceChange` que el programa de origen de datos llama para proporcionar la nueva información al servicio. El programa cliente implementa la operación de servicio `PriceChange` a la que el servicio llama para notificar a todos los suscriptores de un cambio del precio.  
  
```csharp  
// Create a service contract and define the service operations.  
// NOTE: The service operations must be declared explicitly.  
[ServiceContract(SessionMode=SessionMode.Required,  
      CallbackContract=typeof(ISampleClientContract))]  
public interface ISampleContract  
{  
    [OperationContract(IsOneWay = false, IsInitiating=true)]  
    void Subscribe();  
    [OperationContract(IsOneWay = false, IsTerminating=true)]  
    void Unsubscribe();  
    [OperationContract(IsOneWay = true)]  
    void PublishPriceChange(string item, double price,
                                     double change);  
}  
  
public interface ISampleClientContract  
{  
    [OperationContract(IsOneWay = true)]  
    void PriceChange(string item, double price, double change);  
}  
```  
  
 El servicio utiliza un evento de .NET Framework como mecanismo para informar a todos los suscriptores sobre la nueva información. Cuando un cliente se une el servicio llamando a Suscripción, proporciona un controlador de eventos. Cuando un cliente sale de la lista, cancela la suscripción de su controlador de eventos desde el evento. Cuando un origen de datos llama al servicio para crear un informe sobre un cambio de precio, el servicio genera el evento. Esto llama a cada instancia del servicio, una para cada cliente que se ha suscrito, y hace que sus controladores de eventos se ejecuten. Cada controlador de eventos pasa la información a su cliente a través de su función de devolución de llamada.  
  
```csharp
public class PriceChangeEventArgs : EventArgs  
    {  
        public string Item;  
        public double Price;  
        public double Change;  
    }  
  
    // The Service implementation implements your service contract.  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    public class SampleService : ISampleContract  
    {  
        public static event PriceChangeEventHandler PriceChangeEvent;  
        public delegate void PriceChangeEventHandler(object sender, PriceChangeEventArgs e);  
  
        ISampleClientContract callback = null;  
  
        PriceChangeEventHandler priceChangeHandler = null;  
  
        //Clients call this service operation to subscribe.  
        //A price change event handler is registered for this client instance.  
  
        public void Subscribe()  
        {  
            callback = OperationContext.Current.GetCallbackChannel<ISampleClientContract>();  
            priceChangeHandler = new PriceChangeEventHandler(PriceChangeHandler);  
            PriceChangeEvent += priceChangeHandler;  
        }  
  
        //Clients call this service operation to unsubscribe.  
        //The previous price change event handler is unregistered.  
  
        public void Unsubscribe()  
        {  
            PriceChangeEvent -= priceChangeHandler;  
        }  
  
        //Information source clients call this service operation to report a price change.  
        //A price change event is raised. The price change event handlers for each subscriber will execute.  
  
        public void PublishPriceChange(string item, double price, double change)  
        {  
            PriceChangeEventArgs e = new PriceChangeEventArgs();  
            e.Item = item;  
            e.Price = price;  
            e.Change = change;  
            PriceChangeEvent(this, e);  
        }  
  
        //This event handler runs when a PriceChange event is raised.  
        //The client's PriceChange service operation is invoked to provide notification about the price change.  
  
        public void PriceChangeHandler(object sender, PriceChangeEventArgs e)  
        {  
            callback.PriceChange(e.Item, e.Price, e.Change);  
        }  
  
    }  
```  
  
 Al ejecutar el ejemplo, se inician varios clientes. Los clientes se suscriben al servicio. A continuación, ejecute el programa de origen de datos, que envía información al servicio. El servicio pasa la información a todos los suscriptores. Puede ver la actividad en cada consola del cliente que confirma que se ha recibido la información. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>Para ejecutar el ejemplo en el mismo equipo  
  
1. Pruebe que puede tener acceso al servicio mediante un explorador escribiendo la dirección siguiente: `http://localhost/servicemodelsamples/service.svc` . Como respuesta se debe mostrar una página de confirmación.  
  
2. Ejecute Client.exe desde \client\bin\ \\ , en la carpeta específica del lenguaje. La actividad del cliente se muestra en la ventana de consola del cliente. Inicie varios clientes.  
  
3. Ejecute Datasource.exe desde \datasource\bin \\ , en la carpeta específica del lenguaje. La actividad del origen de los datos se muestra en la ventana de la consola. Cuando el origen de datos envía la información al servicio, se debería pasar a cada cliente.  
  
4. Si el cliente, el origen de datos y los programas de servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-machines"></a>Para ejecutar el ejemplo en los equipos  
  
1. Preparar el equipo del servicio:  
  
    1. En el equipo del servicio, cree un directorio virtual denominado ServiceModelSamples. El archivo por lotes Setupvroot.bat del [procedimiento de instalación único para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md) se puede usar para crear el directorio de disco y el directorio virtual.  
  
    2. Copie los archivos de programa de servicio del directorio %SystemDrive%\Inetpub \wwwroot\servicemodelsamples al directorio virtual ServiceModelSamples del equipo de servicio. Asegúrese de incluir los archivos en el directorio \bin.  
  
    3. Pruebe que puede tener acceso al servicio desde el equipo cliente utilizando un explorador.  
  
2. Preparar los equipos cliente:  
  
    1. Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, a los equipos del cliente.  
  
    2. En cada archivo de configuración del cliente, cambie el valor de la dirección de la definición del punto de conexión para que coincida con la nueva dirección de su servicio. Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
3. Preparar el equipo del origen de datos:  
  
    1. Copie los archivos de programa de origen de datos de la carpeta \ datasource \bin\, en la carpeta específica del lenguaje, al equipo del origen de datos.  
  
    2. En el archivo de configuración del origen de datos, cambie el valor de la dirección de la definición del punto de conexión para que coincida con la nueva dirección de su servicio. Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
4. En los equipos cliente, inicie Client.exe desde el símbolo del sistema.  
  
5. En el equipo del origen de datos, inicie Datasource.exe desde un símbolo del sistema.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DesignPatterns/ListBasedPublishSubscribe`
