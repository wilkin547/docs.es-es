---
title: Controlar errores de web HTTP de WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3366ab851c6e6b66a5df94bdb24baad4ae0c8d14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="91d61-102">Controlar errores de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="91d61-102">WCF Web HTTP Error Handling</span></span>
<span data-ttu-id="91d61-103">El control de errores web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] permite devolver errores de los servicios web HTTP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que especifican un código de estado HTTP, así como devolver detalles de error mediante el mismo formato que la operación (por ejemplo, XML o JSON).</span><span class="sxs-lookup"><span data-stu-id="91d61-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP error handling enables you to return errors from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="91d61-104">Controlar errores de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="91d61-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="91d61-105">La clase <xref:System.ServiceModel.Web.WebFaultException> define un constructor que le permite especificar un código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="91d61-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="91d61-106">A continuación, este código de estado se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="91d61-106">This status code is then returned to the client.</span></span> <span data-ttu-id="91d61-107">Una versión genérica de la clase <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> le permite devolver un tipo definido por el usuario que contiene información sobre el error que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="91d61-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="91d61-108">Este objeto personalizado se serializa mediante el formato especificado por la operación y se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="91d61-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="91d61-109">En el siguiente ejemplo, se muestra cómo devolver un código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="91d61-109">The following example shows how to return an HTTP status code.</span></span>  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="91d61-110">En el ejemplo siguiente se muestra cómo devolver un código de estado HTTP e información adicional en un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="91d61-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="91d61-111">`MyErrorDetail` es un tipo definido por el usuario que contiene información adicional sobre el error que se produjo.</span><span class="sxs-lookup"><span data-stu-id="91d61-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
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
  
 <span data-ttu-id="91d61-112">El código anterior devuelve una respuesta HTTP con el código de estado prohibido y un cuerpo que contiene una instancia del objeto `MyErrorDetails`.</span><span class="sxs-lookup"><span data-stu-id="91d61-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="91d61-113">El formato del objeto `MyErrorDetails` se determina mediante los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="91d61-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
-   <span data-ttu-id="91d61-114">El valor del parámetro `ResponseFormat` de la clase <xref:System.ServiceModel.Web.WebGetAttribute> o del atributo de la clase <xref:System.ServiceModel.Web.WebInvokeAttribute> especificados en la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="91d61-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
-   <span data-ttu-id="91d61-115">El valor de <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="91d61-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
-   <span data-ttu-id="91d61-116">El valor de propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> mediante el acceso a <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span><span class="sxs-lookup"><span data-stu-id="91d61-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="91d61-117">cómo estos valores pueden afectar a la aplicación de formato de la operación, vea [Web HTTP de WCF formato](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="91d61-117"> how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="91d61-118"><xref:System.ServiceModel.Web.WebFaultException> es una clase <xref:System.ServiceModel.FaultException> y, por lo tanto, se puede usar como modelo de programación de excepción de errores para los servicios que exponen extremos de SOAP y extremos web HTTP.</span><span class="sxs-lookup"><span data-stu-id="91d61-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d61-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="91d61-119">See Also</span></span>  
 [<span data-ttu-id="91d61-120">Modelo de programación Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="91d61-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="91d61-121">Formato de Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="91d61-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 [<span data-ttu-id="91d61-122">Definición y especificación de errores</span><span class="sxs-lookup"><span data-stu-id="91d61-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)  
 [<span data-ttu-id="91d61-123">Control de excepciones y errores</span><span class="sxs-lookup"><span data-stu-id="91d61-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)  
 [<span data-ttu-id="91d61-124">Envío y recepción de errores</span><span class="sxs-lookup"><span data-stu-id="91d61-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
