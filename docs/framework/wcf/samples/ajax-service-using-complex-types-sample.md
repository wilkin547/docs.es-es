---
title: Servicio AJAX mediante el uso de ejemplo de tipos complejos
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: c284fbef36ee7f6dda725ba9a3db9b98fb1549ed
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="ajax-service-using-complex-types-sample"></a>Servicio AJAX mediante el uso de ejemplo de tipos complejos
Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio ASP.NET JavaScript asincrónico y XML (AJAX) que crea instancias de tipos complejos y envíe entre el servicio y el cliente como JavaScript Object Notation (JSON). Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web. En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo.  
  
 Compatibilidad con AJAX de WCF está optimizado para su uso con ASP.NET AJAX a través del <xref:System.Web.UI.ScriptManager> control. Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea el [muestra AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El servicio en el ejemplo siguiente es un servicio WCF con ningún código específico de AJAX. Dado que no se aplica el atributo <xref:System.ServiceModel.Web.WebGetAttribute>, se utiliza el verbo HTTP predeterminado ("POST"). El servicio tiene una operación, `DoMath`, que devuelve un tipo complejo denominado `MathResult`. El tipo complejo es un tipo de contrato de datos estándar, que tampoco contiene ningún código específico de AJAX.  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 Cree un extremo AJAX en el servicio mediante el uso de la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, exactamente igual que en el ejemplo de servicio AJAX básico.  
  
 El cliente de la página Web ComplexTypeClientPage.aspx contiene código ASP.NET y JavaScript para invocar el servicio cuando el usuario hace clic en el **realizar cálculo** botón en la página. El código para invocar el servicio construye un cuerpo JSON y lo envía utilizando HTTP POST, similar a la [servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) ejemplo.  
  
 Después de que la llamada del servicio tenga éxito, puede tener acceso a los miembros de datos individuales (`sum`, `difference`, `product` y `quotient`) en el objeto JavaScript resultante.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución ComplexTypeAjaxService.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Vaya a http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (no abra ComplexTypeClientPage.aspx en el explorador desde el directorio del proyecto).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>Vea también  
 [Servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
