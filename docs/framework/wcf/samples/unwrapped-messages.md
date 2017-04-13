---
title: "Mensajes desajustados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# Mensajes desajustados
Este ejemplo muestra mensajes desajustados.De forma predeterminada, se da formato al cuerpo del mensaje de manera que se ajusten los parámetros a una operación de servicio.El ejemplo siguiente muestra un mensaje de solicitud `Add` al servicio `ICalculator` en modo ajustado.  
  
```  
<s:Envelope   
    xmlns:s=http://www.w3.org/2003/05/soap-envelope  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
  
```  
  
 El elemento `<Add>` en el cuerpo del mensaje ajusta los parámetros `n2` y `n1`.En contraste, el ejemplo siguiente muestra el mensaje equivalente en el modo desajustado.  
  
```  
<s:Envelope   
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"   
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
  
```  
  
 El mensaje desajustado no ajusta los parámetros `n2` y `n1` en un elemento contenedor, sino que son elementos secundarios directos del elemento del cuerpo de SOAP.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo, se crea un mensaje desajustado aplicando <xref:System.ServiceModel.MessageContractAttribute> al tipo de parámetro de operación de servicio y devuelve el tipo de valor tal y como se muestra en el código de ejemplo siguiente.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 Para permitirle ver los mensajes que se envían y se reciben, este ejemplo utiliza la traza.Además, se ha configurado <xref:System.ServiceModel.WSHttpBinding> sin seguridad para reducir el número de mensajes que registra.  
  
 El registro de traza resultante \(c:\\logs\\Message.log\) puede verse utilizando [Herramienta del visor de seguimiento de servicio \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).Para ver el contenido del mensaje, seleccione **Mensajes** en los paneles de la izquierda y derecha de la herramienta Service Trace Viewer.Los registros de traza en este ejemplo se configuran para que se generen en la carpeta C:\\LOGS.Cree esta carpeta antes de ejecutar el ejemplo y proporcione al usuario permisos de escritura para el servicio de red correspondiente a este directorio.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Cree un directorio C:\\LOGS para registrar los mensajes.Proporcione a los usuarios permisos de escritura de servicio de red para este directorio.  
  
3.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
  
## Vea también