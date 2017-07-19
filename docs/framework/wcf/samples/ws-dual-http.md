---
title: "WS Http dual | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# WS Http dual
El ejemplo Http dual muestra cómo configurar el enlace `WSDualHttpBinding`.Este ejemplo está compuesto de un programa de consola de cliente \(.exe\) y una biblioteca de servicios \(.dll\) hospedados por Internet Information Services \(IIS\).El servicio implementa un contrato dúplex.La interfaz `ICalculatorDuplex`, que expone las operaciones matemáticas \(sumar, restar, multiplicar y dividir\), define el contrato.En este ejemplo, la interfaz `ICalculatorDuplex` permite al cliente realizar las operaciones matemáticas, calculando un resultado en ejecución sobre la sesión.Independientemente, el servicio devuelve los resultados en la interfaz `ICalculatorDuplexCallback`.Un contrato dúplex requiere una sesión, porque se debe establecer un contexto para poner en correlación el conjunto de mensajes que se envían entre el cliente y el servicio.El enlace `WSDualHttpBinding` admite la comunicación dúplex.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`  
  
 Para configurar un extremo de servicio con `WSDualHttpBinding`, especifique el enlace en la configuración del extremo según se muestra.  
  
```  
<endpoint address=""  
         binding="wsDualHttpBinding"  
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
```  
  
 En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.  
  
```  
<system.serviceModel>  
  <client>  
    <endpoint address=  
         "http://localhost/servicemodelsamples/service.svc"   
         binding="wsDualHttpBinding"   
         bindingConfiguration="Binding1"   
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
  </client>  
  
  <bindings>  
    <!-- Configure a WSDualHttpBinding that supports duplex -->  
    <!-- communication. -->  
    <wsDualHttpBinding>  
      <binding name="Binding1"  
               clientBaseAddress="http://localhost:8000/myClient/"  
               useDefaultWebProxy="true"  
               bypassProxyOnLocal="false">  
      </binding>  
    </wsDualHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Presione Entrar en la ventana de cliente para cerrar el cliente.  
  
```  
Press <ENTER> to terminate client once the output is displayed.  
  
Result(100)  
Result(50)  
Result(882.5)  
Result(441.25)  
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)  
  
```  
  
 Al ejecutar el ejemplo, se ven los mensajes devueltos al cliente en la interfaz de devolución de llamada enviada del servicio.Se muestra cada resultado intermedio, seguido por la ecuación completa en la realización de todas las operaciones.Presione ENTRAR para cerrar el cliente.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!IMPORTANT]
    >  Al ejecutar el cliente en una configuración de equipo cruzado, asegúrese de reemplazar el host local en el atributo `address` del elemento [endpoint](http://msdn.microsoft.com/es-es/13aa23b7-2f08-4add-8dbf-a99f8127c017) y en el atributo `clientBaseAddress` del elemento del elemento [\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) con el nombre del equipo adecuado[\<enlace\>](../../../../docs/framework/misc/binding.md), tal y como se muestra en:  
  
    ```  
    <client>  
        <endpoint name = ""  
          address=  
         "http://service_machine_name/servicemodelsamples/service.svc"  
        />  
    </client>  
    ...  
    <wsDualHttpBinding>  
        <binding name="DuplexBinding" clientBaseAddress=  
            "http://client_machine_name:8000/myClient/">  
        </binding>  
    </wsDualHttpBinding>  
    ```  
  
## Vea también