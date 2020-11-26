---
title: Controlar errores de web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: cfbf98c69370764a9526c32459d43521177476e3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239034"
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="03364-102">Controlar errores de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="03364-102">WCF Web HTTP Error Handling</span></span>

<span data-ttu-id="03364-103">El control de errores HTTP Web de Windows Communication Foundation (WCF) permite devolver errores de los servicios Web HTTP de WCF que especifican un código de Estado HTTP y devuelven detalles de error con el mismo formato que la operación (por ejemplo, XML o JSON).</span><span class="sxs-lookup"><span data-stu-id="03364-103">Windows Communication Foundation (WCF) Web HTTP error handling enables you to return errors from WCF Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="03364-104">Controlar errores de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="03364-104">WCF Web HTTP Error Handling</span></span>  

 <span data-ttu-id="03364-105">La clase <xref:System.ServiceModel.Web.WebFaultException> define un constructor que le permite especificar un código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="03364-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="03364-106">A continuación, este código de estado se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="03364-106">This status code is then returned to the client.</span></span> <span data-ttu-id="03364-107">Una versión genérica de la clase <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> le permite devolver un tipo definido por el usuario que contiene información sobre el error que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="03364-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="03364-108">Este objeto personalizado se serializa mediante el formato especificado por la operación y se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="03364-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="03364-109">En el siguiente ejemplo, se muestra cómo devolver un código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="03364-109">The following example shows how to return an HTTP status code.</span></span>  
  
```csharp
public string Operation1()
{
    // Operation logic  
   // ...
   throw new WebFaultException(HttpStatusCode.Forbidden);
}  
```  
  
 <span data-ttu-id="03364-110">En el ejemplo siguiente se muestra cómo devolver un código de estado HTTP e información adicional en un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="03364-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="03364-111">`MyErrorDetail` es un tipo definido por el usuario que contiene información adicional sobre el error que se produjo.</span><span class="sxs-lookup"><span data-stu-id="03364-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
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
  
 <span data-ttu-id="03364-112">El código anterior devuelve una respuesta HTTP con el código de estado prohibido y un cuerpo que contiene una instancia del objeto `MyErrorDetails`.</span><span class="sxs-lookup"><span data-stu-id="03364-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="03364-113">El formato del objeto `MyErrorDetails` se determina mediante los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="03364-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
- <span data-ttu-id="03364-114">El valor del parámetro `ResponseFormat` de la clase <xref:System.ServiceModel.Web.WebGetAttribute> o del atributo de la clase <xref:System.ServiceModel.Web.WebInvokeAttribute> especificados en la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="03364-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
- <span data-ttu-id="03364-115">El valor de <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="03364-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
- <span data-ttu-id="03364-116">El valor de propiedad <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> mediante el acceso a <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span><span class="sxs-lookup"><span data-stu-id="03364-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 <span data-ttu-id="03364-117">Para obtener más información sobre cómo afectan estos valores al formato de la operación, consulte [formato de web http de WCF](wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="03364-117">For more information about how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="03364-118"><xref:System.ServiceModel.Web.WebFaultException> es una clase <xref:System.ServiceModel.FaultException> y, por lo tanto, se puede usar como modelo de programación de excepción de errores para los servicios que exponen extremos de SOAP y extremos web HTTP.</span><span class="sxs-lookup"><span data-stu-id="03364-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03364-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="03364-119">See also</span></span>

- [<span data-ttu-id="03364-120">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="03364-120">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="03364-121">Formato de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="03364-121">WCF Web HTTP Formatting</span></span>](wcf-web-http-formatting.md)
- [<span data-ttu-id="03364-122">Definición y especificación de errores</span><span class="sxs-lookup"><span data-stu-id="03364-122">Defining and Specifying Faults</span></span>](../defining-and-specifying-faults.md)
- [<span data-ttu-id="03364-123">Administración de excepciones y errores</span><span class="sxs-lookup"><span data-stu-id="03364-123">Handling Exceptions and Faults</span></span>](../extending/handling-exceptions-and-faults.md)
- [<span data-ttu-id="03364-124">Envío y recepción de errores</span><span class="sxs-lookup"><span data-stu-id="03364-124">Sending and Receiving Faults</span></span>](../sending-and-receiving-faults.md)
