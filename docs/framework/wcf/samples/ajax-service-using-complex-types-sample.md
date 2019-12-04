---
title: Servicio AJAX mediante el uso de ejemplo de tipos complejos
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: be8db36be7ed1639d839113174fdb95505466534
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716235"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="8d040-102">Servicio AJAX mediante el uso de ejemplo de tipos complejos</span><span class="sxs-lookup"><span data-stu-id="8d040-102">AJAX Service Using Complex Types Sample</span></span>

<span data-ttu-id="8d040-103">En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript asincrónico y XML (AJAX) ASP.NET que crea instancias de tipos complejos y los envía entre el servicio y el cliente como notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="8d040-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8d040-104">Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web.</span><span class="sxs-lookup"><span data-stu-id="8d040-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="8d040-105">Este ejemplo se basa en el ejemplo de [servicio Ajax básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) .</span><span class="sxs-lookup"><span data-stu-id="8d040-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>

<span data-ttu-id="8d040-106">La compatibilidad de AJAX en WCF está optimizada para su uso con ASP.NET AJAX a través del control de <xref:System.Web.UI.ScriptManager>.</span><span class="sxs-lookup"><span data-stu-id="8d040-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="8d040-107">Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="8d040-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8d040-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8d040-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="8d040-109">El servicio en el ejemplo siguiente es un servicio WCF sin código específico de AJAX.</span><span class="sxs-lookup"><span data-stu-id="8d040-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="8d040-110">Dado que no se aplica el atributo <xref:System.ServiceModel.Web.WebGetAttribute>, se utiliza el verbo HTTP predeterminado ("POST").</span><span class="sxs-lookup"><span data-stu-id="8d040-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="8d040-111">El servicio tiene una operación, `DoMath`, que devuelve un tipo complejo denominado `MathResult`.</span><span class="sxs-lookup"><span data-stu-id="8d040-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="8d040-112">El tipo complejo es un tipo de contrato de datos estándar, que tampoco contiene ningún código específico de AJAX.</span><span class="sxs-lookup"><span data-stu-id="8d040-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>

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

<span data-ttu-id="8d040-113">Cree un extremo AJAX en el servicio mediante el uso de la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, exactamente igual que en el ejemplo de servicio AJAX básico.</span><span class="sxs-lookup"><span data-stu-id="8d040-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="8d040-114">La página web del cliente ComplexTypeClientPage. aspx contiene el código ASP.NET y JavaScript para invocar el servicio cuando el usuario hace clic en el botón **realizar cálculo** de la página.</span><span class="sxs-lookup"><span data-stu-id="8d040-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="8d040-115">El código para invocar el servicio construye un cuerpo JSON y lo envía mediante HTTP POST, similar al [servicio Ajax mediante el ejemplo http post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) .</span><span class="sxs-lookup"><span data-stu-id="8d040-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>

<span data-ttu-id="8d040-116">Después de que la llamada del servicio tenga éxito, puede tener acceso a los miembros de datos individuales (`sum`, `difference`, `product` y `quotient`) en el objeto JavaScript resultante.</span><span class="sxs-lookup"><span data-stu-id="8d040-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>

```javascript
function onSuccess(mathResult){
     document.getElementById("sum").value = mathResult.sum;
     document.getElementById("difference").value = mathResult.difference;
     document.getElementById("product").value = mathResult.product;
     document.getElementById("quotient").value = mathResult.quotient;
}
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8d040-117">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d040-117">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="8d040-118">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8d040-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="8d040-119">Compile la solución ComplexTypeAjaxService. sln tal y como se describe en [Building the Windows Communication Foundation samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8d040-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="8d040-120">Vaya a `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (no abra ComplexTypeClientPage. aspx en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="8d040-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d040-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8d040-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8d040-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8d040-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="8d040-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d040-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d040-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8d040-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a><span data-ttu-id="8d040-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d040-125">See also</span></span>

- [<span data-ttu-id="8d040-126">Servicio AJAX básico</span><span class="sxs-lookup"><span data-stu-id="8d040-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
