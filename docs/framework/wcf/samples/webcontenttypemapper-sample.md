---
title: Ejemplo de WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: a51d03fab5c6499a0e9685e01a9bbace1c11f28a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594561"
---
# <a name="webcontenttypemapper-sample"></a>Ejemplo de WebContentTypeMapper
Este ejemplo muestra cómo asignar los nuevos tipos de contenido a los formatos de cuerpo de mensaje de Windows Communication Foundation (WCF).  
  
 El <xref:System.ServiceModel.Description.WebHttpEndpoint> elemento se conecta en el codificador de mensajes Web, que permite a WCF recibir mensajes binarios JSON, XML o sin formato en el mismo punto de conexión. El codificador determina el formato del cuerpo del mensaje examinando el tipo de contenido del Http de la solicitud. Este ejemplo incluye la clase <xref:System.ServiceModel.Channels.WebContentTypeMapper>, que permite al usuario controlar la asignación entre el tipo de contenido y el formato del cuerpo.  
  
 WCF proporciona un conjunto de asignaciones predeterminadas para los tipos de contenido. Por ejemplo, `application/json` se asigna a JSON y `text/xml` se asigna a XML. Cualquier tipo de contenido que no está asignado a JSON o a XML, está asignado al formato binario sin formato.  
  
 En algunos escenarios (por ejemplo, estilo de inserción API), el programador del servicio no controla el tipo de contenido devuelto por el cliente. Por ejemplo, los clientes podrían devolver JSON como `text/javascript` en lugar de `application/json`. En este caso, el programador del servicio debe proporcionar un tipo que deriva de <xref:System.ServiceModel.Channels.WebContentTypeMapper> para administrar correctamente el tipo de contenido determinado, como se muestra en el código de muestra siguiente.  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 El tipo debe reemplazar el método <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>. El método debe evaluar el argumento `contentType` y devolver uno de los valores siguientes: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>o <xref:System.ServiceModel.Channels.WebContentFormat.Default>. El devolver el <xref:System.ServiceModel.Channels.WebContentFormat.Default> difiere las asignaciones de codificador del mensaje de web predeterminadas. En el código de ejemplo anterior, el tipo de contenido `text/javascript` está asignado a JSON y todas las demás asignaciones siguen estando sin modificar.  
  
 Para utilizar la clase `JsonContentTypeMapper`, utilice lo siguiente en el archivo Web.config:  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Para comprobar el requisito para utilizar JsonContentTypeMapper, quite el atributo contentTypeMapper del archivo de configuración anterior. La página del cliente no se carga al intentar utilizar `text/javascript` para enviar el contenido JSON.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Compile la solución WebContentTypeMapperSample. sln tal y como se describe en [Building the Windows Communication Foundation samples](building-the-samples.md).  
  
3. Vaya a `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (no abra JCTMClientPage. htm en el explorador desde el directorio del proyecto).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
