---
description: 'Más información sobre: control de errores de Web HTTP de WCF'
title: Controlar errores de web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 88483c249bc1b6b866517ca10b348c0885fc34fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779485"
---
# <a name="wcf-web-http-error-handling"></a>Controlar errores de web HTTP de WCF

El control de errores HTTP Web de Windows Communication Foundation (WCF) permite devolver errores de los servicios Web HTTP de WCF que especifican un código de Estado HTTP y devuelven detalles de error con el mismo formato que la operación (por ejemplo, XML o JSON).  
  
## <a name="wcf-web-http-error-handling"></a>Controlar errores de web HTTP de WCF  

 La clase <xref:System.ServiceModel.Web.WebFaultException> define un constructor que le permite especificar un código de estado HTTP. A continuación, este código de estado se devuelve al cliente. Una versión genérica de la clase <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> le permite devolver un tipo definido por el usuario que contiene información sobre el error que se ha producido. Este objeto personalizado se serializa mediante el formato especificado por la operación y se devuelve al cliente. En el siguiente ejemplo, se muestra cómo devolver un código de estado HTTP.  
  
```csharp
public string Operation1()
{
    // Operation logic  
   // ...
   throw new WebFaultException(HttpStatusCode.Forbidden);
}  
```  
  
 En el ejemplo siguiente se muestra cómo devolver un código de estado HTTP e información adicional en un tipo definido por el usuario. `MyErrorDetail` es un tipo definido por el usuario que contiene información adicional sobre el error que se produjo.  
  
```csharp
public string Operation2()
{
   // Operation logic  
   // ...
   MyErrorDetail detail = new MyErrorDetail()
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
  
 Para obtener más información sobre cómo afectan estos valores al formato de la operación, consulte [formato de web http de WCF](wcf-web-http-formatting.md).  
  
 <xref:System.ServiceModel.Web.WebFaultException> es una clase <xref:System.ServiceModel.FaultException> y, por lo tanto, se puede usar como modelo de programación de excepción de errores para los servicios que exponen extremos de SOAP y extremos web HTTP.  
  
## <a name="see-also"></a>Vea también

- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
- [Formato de web HTTP de WCF](wcf-web-http-formatting.md)
- [Definición y especificación de errores](../defining-and-specifying-faults.md)
- [Administración de excepciones y errores](../extending/handling-exceptions-and-faults.md)
- [Envío y recepción de errores](../sending-and-receiving-faults.md)
