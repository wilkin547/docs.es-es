---
title: "Generador de canales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Generador de canales
Este ejemplo muestra cómo una aplicación cliente puede crear un canal con la clase <xref:System.ServiceModel.ChannelFactory> en lugar de un cliente generado.Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa un servicio de calculadora.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo utiliza la clase <xref:System.ServiceModel.ChannelFactory%601> para crear un canal a un extremo de servicio.Normalmente, para crear un canal a un extremo de servicio genera un tipo de cliente con [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) y crea una instancia del tipo generado.También puede crear un canal utilizando la clase <xref:System.ServiceModel.ChannelFactory%601>, tal y como se muestra en este ejemplo.El servicio creado por el código de ejemplo siguiente es idéntico al servicio en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  Si está ejecutando este ejemplo en un escenario con varios equipos, debe reemplazar el "host local" en el código anterior con el nombre completo del equipo que está ejecutando el servicio.Este ejemplo no utiliza la configuración para establecer la dirección del extremo, por lo que se debe hacer en el código.  
  
 Una vez creado el canal, se pueden invocar operaciones de servicio de la misma manera que con un cliente generado.  
  
```  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
 Para cerrar el canal, se debe convertir primero a una interfaz <xref:System.ServiceModel.IClientChannel>.Esto es porque cuando se genera el canal se declara en la aplicación cliente utilizando la interfaz `ICalculator`, que cuenta con métodos como `Add` y `Subtract` pero no `Close`.El método `Close` se origina en la interfaz <xref:System.ServiceModel.ICommunicationObject>.  
  
```  
// Close the channel.  
 ((IClientChannel)client).Close();  
  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Presione ENTRAR en la ventana de cliente para cerrar la aplicación del cliente.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).Observe que este ejemplo no permite la publicación de metadatos.Debe habilitarla primero para este ejemplo con objeto de regenerar el tipo de cliente.  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Para ejecutar el ejemplo en varios equipos  
  
1.  Reemplace el "host local" en el código siguiente con el nombre completo del equipo que está ejecutando el servicio.  
  
    ```  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
  
## Vea también