---
title: Controlar errores de web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 834c642e36e1551081dbe1f14529ed7596df1360
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935491"
---
# <a name="wcf-web-http-error-handling"></a>Controlar errores de web HTTP de WCF
Control de errores de Web HTTP de Windows Communication Foundation (WCF) le permite devolver errores de servicios Web HTTP de WCF que especifican un código de estado HTTP y devuelven detalles de error con el mismo formato que la operación (por ejemplo, XML o JSON).  
  
## <a name="wcf-web-http-error-handling"></a>Controlar errores de web HTTP de WCF  
 La clase <xref:System.ServiceModel.Web.WebFaultException> define un constructor que le permite especificar un código de estado HTTP. A continuación, este código de estado se devuelve al cliente. Una versión genérica de la clase <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> le permite devolver un tipo definido por el usuario que contiene información sobre el error que se ha producido. Este objeto personalizado se serializa mediante el formato especificado por la operación y se devuelve al cliente. En el siguiente ejemplo, se muestra cómo devolver un código de estado HTTP.  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 En el ejemplo siguiente se muestra cómo devolver un código de estado HTTP e información adicional en un tipo definido por el usuario. `MyErrorDetail` es un tipo definido por el usuario que contiene información adicional sobre el error que se produjo.  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 El código anterior devuelve una respuesta HTTP con el código de estado prohibido y un cuerpo que contiene una instancia del objeto `MyErrorDetails`. El formato del objeto `MyErrorDetails` se determina mediante los elementos siguientes:  
  
- El valor del parámetro `ResponseFormat` de la clase <xref:System.ServiceModel.Web.WebGetAttribute> o del atributo de la clase <xref:System.ServiceModel.Web.WebInvokeAttribute> especificados en la operación de servicio.  
  
- El valor de <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.  
  
- El valor de propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> mediante el acceso a <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.  
  
 Para obtener más información acerca de cómo afectan estos valores al formato de la operación, vea [WCF Web HTTP formato](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).  
  
 <xref:System.ServiceModel.Web.WebFaultException> es una clase <xref:System.ServiceModel.FaultException> y, por lo tanto, se puede usar como modelo de programación de excepción de errores para los servicios que exponen extremos de SOAP y extremos web HTTP.  
  
## <a name="see-also"></a>Vea también

- [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [Formato de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [Definición y especificación de errores](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [Administración de excepciones y errores](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [Envío y recepción de errores](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
