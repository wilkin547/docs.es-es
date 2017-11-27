---
title: "Activación NamedPipe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 55594e1505e60ede8d7c6abcbd8a9cf9a1f739bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipe-activation"></a>Activación NamedPipe
Este ejemplo muestra cómo hospedar un servicio que utiliza el servicio de activación de procesos de Windows (WAS) para activar un servicio que se comunica a través de las canalizaciones de los nombres. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) y requiere [!INCLUDE[wv](../../../../includes/wv-md.md)] para que se ejecute.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 El ejemplo está compuesto de un programa (.exe) de consola de cliente y una biblioteca de servicios (.dll) hospedados en un proceso de trabajo activado por el servicio de activación de procesos de Windows (WAS). La actividad del cliente es visible en la ventana de la consola.  
  
 El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (Sumar, Restar, Multiplicar y Dividir), define el contrato, tal ycomo se muestra en el código muestra siguiente.  
  
```  
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
  
 El cliente realiza las solicitudes sincrónicas a una operación matemática determinada y la implementación del servicio calcula y devuelve el resultado adecuado.  
  
```  
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
  
 El ejemplo utiliza un enlace `netNamedPipeBinding` modificado sin seguridad. El enlace se especifica en los archivos de configuración para el cliente y servicio. El tipo de enlace se especifica para el servicio en el atributo `binding` del elemento del extremo, tal y como se explica en el ejemplo siguiente de configuración.  
  
 Si desea utilizar un enlace seguro de canalización con nombre, cambie el modo de seguridad del servidor a la configuración de seguridad deseada y ejecute de nuevo svcutil.exe en el cliente para obtener un archivo de configuración del cliente actualizado.  
  
```xml  
<system.serviceModel>  
        <services>  
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
  
        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->  
        <endpoint address=""   
                  binding="netNamedPipeBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexNamedPipeBinding"  
                  contract="IMetadataExchange" />  
      </service>  
        </services>      
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="Binding1" >  
                    <security mode = "None">  
                    </security>  
                </binding >  
            </netNamedPipeBinding>  
        </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 La información de extremo del cliente se configura como se muestra en el código muestra siguiente.  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <endpoint name=""  
                          address="net.pipe://localhost/servicemodelsamples/service.svc"   
                          binding="netNamedPipeBinding"   
                          bindingConfiguration="Binding1"   
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
    <bindings>  
  
      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.  
            Each property is configured with the default value.   -->  
  
      <netNamedPipeBinding>  
        <binding name="Binding1"   
                         maxBufferSize="65536"  
                         maxConnections="10">  
          <security mode = "None">  
          </security>  
        </binding >  
  
      </netNamedPipeBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que [!INCLUDE[iisver](../../../../includes/iisver-md.md)] está instalado. [!INCLUDE[iisver](../../../../includes/iisver-md.md)] es necesario para la activación de WAS.  
  
2.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
     Además, debe instalar los componentes de activación que no son HTTP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
    1.  Desde el **iniciar** menú, elija **el Panel de Control**.  
  
    2.  Seleccione **programas y características**.  
  
    3.  Haga clic en **activar o desactivar el componentes de Windows**.  
  
    4.  Expanda el **Microsoft .NET Framework 3.0** nodo y compruebe el **activación no HTTP de Windows Communication Foundation** característica.  
  
3.  Configure el servicio de activación de procesos de Windows (WAS) para admitir la activación de la canalización con nombre.  
  
     Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado AddNetPipeSiteBinding.cmd localizado en el directorio de ejemplo.  
  
    1.  Para admitir la activación de net.pipe, el sitio web predeterminado se debe enlazar primero al protocolo net.pipe. Esto se puede hacer utilizando appcmd.exe, que se instala con el conjunto de herramientas de administración de IIS 7.0. Desde un símbolo del sistema con permisos elevados (administrador), ejecute el comando siguiente.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        -+bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  Este comando es una sola línea de texto.  
  
         Este comando agrega un enlace del sitio de net.pipe al sitio web predeterminado.  
  
    2.  Aunque todas las aplicaciones dentro de un sitio comparten un enlace net.pipe común, cada aplicación puede habilitar la compatibilidad net.pipe individualmente. Para habilitar net.pipe para la aplicación /servicemodelsamples, ejecute el comando siguiente desde un símbolo del sistema con permisos elevados.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe  
        ```  
  
        > [!NOTE]
        >  Este comando es una sola línea de texto.  
  
         Este comando habilita la aplicación /servicemodelsamples para tener acceso utilizando http://localhost/servicemodelsamples y net.tcp://localhost/servicemodelsamples.  
  
4.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Quite el enlace del sitio de net.pipe que ha agregado para obtener este ejemplo.  
  
     Para su comodidad, los dos pasos siguientes se implementan en un archivo por lotes denominado RemoveNetPipeSiteBinding.cmd que se encuentra en el directorio de ejemplo:  
  
    1.  Quite net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Este comando se debe escribir como una línea de texto única.  
  
    2.  Quite el enlace del sitio net.tcp ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  Este comando se debe escribir en una sola línea de texto.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
