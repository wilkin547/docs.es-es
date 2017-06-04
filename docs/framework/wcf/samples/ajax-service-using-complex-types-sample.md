---
title: "Servicio AJAX mediante el uso de ejemplo de tipos complejos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Servicio AJAX mediante el uso de ejemplo de tipos complejos
Este ejemplo muestra cómo utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para crear un servicio ASP.NET JavaScript Asincrónico y XML \(AJAX\) que cree instancias de tipos complejos y los envíe entre el servicio y cliente como notación de objeto JavaScript \(JSON\).Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web.Este ejemplo se basa en el ejemplo [Servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
 La compatibilidad de AJAX en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se optimiza para su uso con ASP.NET AJAX a través del control <xref:System.Web.UI.ScriptManager>.Para obtener un ejemplo sobre cómo usar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con ASP.NET AJAX, vea [AJAX Samples](http://msdn.microsoft.com/es-es/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El servicio en el ejemplo siguiente es un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin el código específico de AJAX.Dado que no se aplica el atributo <xref:System.ServiceModel.Web.WebGetAttribute>, se utiliza el verbo HTTP predeterminado \("POST"\).El servicio tiene una operación, `DoMath`, que devuelve un tipo complejo denominado `MathResult`.El tipo complejo es un tipo de contrato de datos estándar, que tampoco contiene ningún código específico de AJAX.  
  
```  
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
  
 El cliente de la página web ComplexTypeClientPage.aspx contiene código ASP.NET y JavaScript para invocar el servicio cuando el usuario hace clic en el botón **Realizar cálculo** de la página.El código para invocar el servicio construye un cuerpo de JSON y lo envía utilizando HTTP POST, similar al ejemplo [Servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Después de que la llamada del servicio tenga éxito, puede tener acceso a los miembros de datos individuales \(`sum`, `difference`, `product` y `quotient`\) en el objeto JavaScript resultante.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución ComplexTypeAjaxService.sln tal y como se describe en [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navegue a http:\/\/localhost\/ServiceModelSamples\/ComplexTypeClientPage.aspx \(no abra ComplexTypeClientPage.aspx en el explorador del directorio del proyecto\).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## Vea también  
 [Servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md)