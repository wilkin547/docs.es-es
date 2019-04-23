---
title: Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 6114fa90b10a5d0cacb60a7ad40f63fae776e174
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337427"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a><span data-ttu-id="0959a-102">Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="0959a-102">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>
<span data-ttu-id="0959a-103">En este tema se describe los procedimientos para migrar un servicio AJAX de ASP.NET básico a un servicio de Windows Communication Foundation (WCF) con AJAX habilitado equivalente.</span><span class="sxs-lookup"><span data-stu-id="0959a-103">This topic outlines procedures to migrate a basic ASP.NET AJAX service to an equivalent AJAX-enabled Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="0959a-104">Muestra cómo crear una versión WCF funcionalmente equivalente de un servicio AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0959a-104">It shows how to create a functionally equivalent WCF version of an ASP.NET AJAX service.</span></span> <span data-ttu-id="0959a-105">Los dos servicios, a continuación, se pueden usar en paralelo, o el servicio de WCF puede utilizarse para reemplazar el servicio de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0959a-105">The two services can then be used side by side, or the WCF service can be used to replace the ASP.NET AJAX service.</span></span>

 <span data-ttu-id="0959a-106">Migración de ASP.NET AJAX existente servicio a un servicio AJAX de WCF le ofrece las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="0959a-106">Migrating an existing ASP.NET AJAX service to a WCF AJAX service gives you the following benefits:</span></span>

-   <span data-ttu-id="0959a-107">Puede exponer su servicio de AJAX como un servicio SOAP con una configuración adicional mínima.</span><span class="sxs-lookup"><span data-stu-id="0959a-107">You can expose your AJAX service as a SOAP service with minimal extra configuration.</span></span>

-   <span data-ttu-id="0959a-108">Puede beneficiarse de las características WCF, como el seguimiento y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0959a-108">You can benefit from WCF features such as tracing, and so on.</span></span>

 <span data-ttu-id="0959a-109">Los procedimientos siguientes suponen que está usando Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="0959a-109">The following procedures assume that you are using Visual Studio 2012.</span></span>

 <span data-ttu-id="0959a-110">El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo que sigue a los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="0959a-110">The code that results from the procedures outlined in this topic is provided in the example following the procedures.</span></span>

 <span data-ttu-id="0959a-111">Para obtener más información acerca de cómo exponer un servicio WCF a través de un extremo con AJAX habilitado, consulte el [Cómo: Usar configuración para agregar un extremo ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) tema.</span><span class="sxs-lookup"><span data-stu-id="0959a-111">For more information about exposing a WCF service through an AJAX-enabled endpoint, see the [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) topic.</span></span>

### <a name="to-create-and-test-the-aspnet-web-service-application"></a><span data-ttu-id="0959a-112">Crear y probar la aplicación de servicio web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0959a-112">To create and test the ASP.NET Web service application</span></span>

1. <span data-ttu-id="0959a-113">Abra Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="0959a-113">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="0959a-114">Desde el **archivo** menú, seleccione **New**, a continuación, **proyecto**, a continuación, **Web**y, a continuación, seleccione **aplicación de servicio Web de ASP.NET** .</span><span class="sxs-lookup"><span data-stu-id="0959a-114">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Service Application**.</span></span>

3. <span data-ttu-id="0959a-115">Denomine el proyecto `ASPHello` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0959a-115">Name the project `ASPHello` and click **OK**.</span></span>

4. <span data-ttu-id="0959a-116">Quite los comentarios de línea en el archivo Service1.asmx.cs que contiene `System.Web.Script.Services.ScriptService]` para habilitar AJAX en este servicio.</span><span class="sxs-lookup"><span data-stu-id="0959a-116">Uncomment the line in the Service1.asmx.cs file that contains `System.Web.Script.Services.ScriptService]` to enable AJAX for this service.</span></span>

5. <span data-ttu-id="0959a-117">Desde el **compilar** menú, seleccione **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="0959a-117">From the **Build** menu, select **Build Solution**.</span></span>

6. <span data-ttu-id="0959a-118">En el menú **Depurar**, seleccione **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="0959a-118">From the **Debug** menu, select **Start Without Debugging**.</span></span>

7. <span data-ttu-id="0959a-119">En la página web generada, seleccione la operación `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="0959a-119">On the Web page generated, select the `HelloWorld` operation.</span></span>

8. <span data-ttu-id="0959a-120">Haga clic en el **Invoke** situado en la `HelloWorld` página de prueba.</span><span class="sxs-lookup"><span data-stu-id="0959a-120">Click the **Invoke** button on the `HelloWorld` test page.</span></span> <span data-ttu-id="0959a-121">Debería recibir la siguiente respuesta XML.</span><span class="sxs-lookup"><span data-stu-id="0959a-121">You should receive the following XML response.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. <span data-ttu-id="0959a-122">Esta respuesta confirma que ha recibido un servicio de AJAX de ASP.NET que funciona y, en particular, que el servicio ha expuesto un punto de conexión en Service1.asmx/HelloWorld que responde a la solicitud HTTP POST y devuelve XML.</span><span class="sxs-lookup"><span data-stu-id="0959a-122">This response confirms that you now have a functioning ASP.NET AJAX service and, in particular, that the service has now exposed an endpoint at Service1.asmx/HelloWorld that responds to HTTP POST requests and returns XML.</span></span>

     <span data-ttu-id="0959a-123">Ahora está listo para convertir este servicio para utilizar un servicio AJAX de WCF.</span><span class="sxs-lookup"><span data-stu-id="0959a-123">Now you are ready to convert this service to use a WCF AJAX service.</span></span>

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a><span data-ttu-id="0959a-124">Para crear una aplicación de servicio de AJAX de WCF equivalente.</span><span class="sxs-lookup"><span data-stu-id="0959a-124">To create an equivalent WCF AJAX service application</span></span>

1. <span data-ttu-id="0959a-125">Haga clic en el **ASPHello** del proyecto y seleccione **agregar**, a continuación, **nuevo elemento**y, a continuación, **servicio WCF habilitado para AJAX**.</span><span class="sxs-lookup"><span data-stu-id="0959a-125">Right-click the **ASPHello** project and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>

2. <span data-ttu-id="0959a-126">Nombre del servicio `WCFHello` y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="0959a-126">Name the service `WCFHello` and click **Add**.</span></span>

3. <span data-ttu-id="0959a-127">Abra el archivo WCFHello.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="0959a-127">Open the WCFHello.svc.cs file.</span></span>

4. <span data-ttu-id="0959a-128">En Service1.asmx.cs, copie la siguiente implementación de la `HelloWorld` operación.</span><span class="sxs-lookup"><span data-stu-id="0959a-128">From Service1.asmx.cs, copy the following implementation of the `HelloWorld` operation.</span></span>

    ```
    public string HelloWorld()
    {
         return "Hello World";
    }
    ```

5. <span data-ttu-id="0959a-129">Pegar implementación copiada de la `HelloWorld` operación en el archivo WCFHello.svc.cs en lugar de en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0959a-129">Paste to copied implementation of the `HelloWorld` operation into the WCFHello.svc.cs file in place of the following code.</span></span>

    ```
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. <span data-ttu-id="0959a-130">Especifique el `Namespace` atributo <xref:System.ServiceModel.ServiceContractAttribute> como `WCFHello`.</span><span class="sxs-lookup"><span data-stu-id="0959a-130">Specify the `Namespace` attribute for <xref:System.ServiceModel.ServiceContractAttribute> as `WCFHello`.</span></span>

    ```
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. <span data-ttu-id="0959a-131">Agregar el <xref:System.ServiceModel.Web.WebInvokeAttribute> a la `HelloWorld` operación y establezca el <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> propiedad para devolver <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span><span class="sxs-lookup"><span data-stu-id="0959a-131">Add the <xref:System.ServiceModel.Web.WebInvokeAttribute> to the `HelloWorld` operation and set the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> property to return <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span></span> <span data-ttu-id="0959a-132">Observe que, si no se establece, el tipo devuelto predeterminado es <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="0959a-132">Note that, if not set, the default return type is <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span>

    ```
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. <span data-ttu-id="0959a-133">Desde el **compilar** menú, seleccione **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="0959a-133">From the **Build** menu, select **Build Solution**.</span></span>

9. <span data-ttu-id="0959a-134">Abra el archivo Wcfhello.svc.cs y desde el **depurar** menú, seleccione **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="0959a-134">Open the WCFHello.svc file and from the **Debug** menu, select **Start Without Debugging**.</span></span>

10. <span data-ttu-id="0959a-135">El servicio expone un punto de conexión en `WCFHello.svc/HelloWorld`, que responde a solicitudes HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="0959a-135">The service now exposes an endpoint at `WCFHello.svc/HelloWorld`, which responds to HTTP POST requests.</span></span> <span data-ttu-id="0959a-136">Las solicitudes HTTP POST no se pueden probar desde el explorador, pero los puntos de conexión devuelven XML a continuación de XML.</span><span class="sxs-lookup"><span data-stu-id="0959a-136">HTTP POST requests cannot be tested from the browser, but the endpoint returns XML following XML.</span></span>

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. <span data-ttu-id="0959a-137">El `WCFHello.svc/HelloWorld` y `Service1.aspx/HelloWorld` puntos de conexión ahora son funcionalmente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0959a-137">The `WCFHello.svc/HelloWorld` and the `Service1.aspx/HelloWorld` endpoints are now functionally equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="0959a-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0959a-138">Example</span></span>
 <span data-ttu-id="0959a-139">El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0959a-139">The code that results from the procedures outlined in this topic is provided in the following example.</span></span>

```csharp
//This is the ASP.NET code in the Service1.asmx.cs file.

using System;
using System.Collections;
using System.ComponentModel;
using System.Data;
using System.Linq;
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
using System.Xml.Linq;
using System.Web.Script.Services;

namespace ASPHello
{
    /// <summary>
    /// Summary description for Service1.
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.
    [System.Web.Script.Services.ScriptService]
    public class Service1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }
    }
}

//This is the WCF code in the WCFHello.svc.cs file.
using System;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.ServiceModel.Web;

namespace ASPHello
{
    [ServiceContract(Namespace = "WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class WCFHello
    {
        // Add [WebInvoke] attribute to use HTTP GET.
        [OperationContract]
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // Add more operations here and mark them with [OperationContract].
    }
}
```

 <span data-ttu-id="0959a-140">El tipo <xref:System.Xml.XmlDocument> no es compatible con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque no es serializable por <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0959a-140">The <xref:System.Xml.XmlDocument> type is not supported by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because it is not serializable by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="0959a-141">Puede utilizar un tipo <xref:System.Xml.Linq.XDocument> o serializar <xref:System.Xml.XmlDocument.DocumentElement%2A> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0959a-141">You can use either an <xref:System.Xml.Linq.XDocument> type, or serialize the <xref:System.Xml.XmlDocument.DocumentElement%2A> instead.</span></span>

 <span data-ttu-id="0959a-142">Si los servicios Web ASMX se están actualizando y migran en paralelo a los servicios WCF, evite asignar dos tipos en el mismo nombre en el cliente.</span><span class="sxs-lookup"><span data-stu-id="0959a-142">If ASMX Web services are being upgraded and migrated side-by-side to WCF services, avoid mapping two types to the same name on the client.</span></span> <span data-ttu-id="0959a-143">Esto produce una excepción en los serializadores si el mismo tipo se utiliza en <xref:System.Web.Services.WebMethodAttribute> y <xref:System.ServiceModel.ServiceContractAttribute>:</span><span class="sxs-lookup"><span data-stu-id="0959a-143">This causes an exception in serializers if the same type is used in a <xref:System.Web.Services.WebMethodAttribute> and a <xref:System.ServiceModel.ServiceContractAttribute>:</span></span>

-   <span data-ttu-id="0959a-144">Si se agrega primero el servicio WCF, invocar el método de servicio Web ASMX produce una excepción en <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> porque la definición de estilo WCF del orden en el proxy tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="0959a-144">If WCF service is added first, invoking the method on ASMX Web Service causes exception in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> because the WCF style definition of the order in the proxy takes precedence.</span></span>

-   <span data-ttu-id="0959a-145">Si primero se agrega el servicio Web ASMX, invocar el método en el servicio WCF produce una excepción en <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque la definición de estilo del servicio Web del orden en el proxy tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="0959a-145">If ASMX Web Service is added first, invoking method on WCF service causes exception in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because the Web Service style definition of the order in the proxy takes precedence.</span></span>

 <span data-ttu-id="0959a-146">Hay diferencias significativas en el comportamiento entre <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y el AJAX de ASP.NET <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0959a-146">There are significant differences in behavior between the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> and the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span></span> <span data-ttu-id="0959a-147">Por ejemplo, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> representa un diccionario como una matriz de pares clave-valor, mientras que el <xref:System.Web.Script.Serialization.JavaScriptSerializer> de AJAX de ASP.NET representa un diccionario como objetos JSON reales.</span><span class="sxs-lookup"><span data-stu-id="0959a-147">For example, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> represents a dictionary as an array of key/value pairs, whereas the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> represents a dictionary as actual JSON objects.</span></span> <span data-ttu-id="0959a-148">Por tanto lo siguiente es el diccionario representado en ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="0959a-148">So the following is the dictionary represented in ASP.NET AJAX.</span></span>

```
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 <span data-ttu-id="0959a-149">Este diccionario se representa en objetos JSON como se muestra en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="0959a-149">This dictionary is represented in JSON objects as shown in the following list:</span></span>

-   <span data-ttu-id="0959a-150">[{"Clave":"uno","Valor":1}, {"Clave":"dos","Valor":2}] por <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span><span class="sxs-lookup"><span data-stu-id="0959a-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span></span>

-   <span data-ttu-id="0959a-151">{"uno": 1, "dos": 2} por el AJAX de ASP.NET <xref:System.Web.Script.Serialization.JavaScriptSerializer></span><span class="sxs-lookup"><span data-stu-id="0959a-151">{"one":1,"two":2} by the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer></span></span>

 <span data-ttu-id="0959a-152"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> es más eficaz en el sentido de que puede controlar los diccionarios cuyo tipo de clave no es de cadena, mientras que <xref:System.Web.Script.Serialization.JavaScriptSerializer> no puede.</span><span class="sxs-lookup"><span data-stu-id="0959a-152">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is more powerful in the sense that it can handle dictionaries where the key type is not string, while the <xref:System.Web.Script.Serialization.JavaScriptSerializer> cannot.</span></span> <span data-ttu-id="0959a-153">Pero el último es más compatible con JSON.</span><span class="sxs-lookup"><span data-stu-id="0959a-153">But the latter is more JSON-friendly.</span></span>

 <span data-ttu-id="0959a-154">Las diferencias significativas entre estos serializadores se resumen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="0959a-154">The significant differences between these serializers are summarized in the following table.</span></span>

|<span data-ttu-id="0959a-155">Categoría de diferencias</span><span class="sxs-lookup"><span data-stu-id="0959a-155">Category of Differences</span></span>|<span data-ttu-id="0959a-156">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="0959a-156">DataContractJsonSerializer</span></span>|<span data-ttu-id="0959a-157">JavaScriptSerializer de AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0959a-157">ASP.NET AJAX JavaScriptSerializer</span></span>|
|-----------------------------|--------------------------------|---------------------------------------|
|<span data-ttu-id="0959a-158">Deserializar el búfer vacío (nuevo byte [0]) en <xref:System.Object> (o <xref:System.Uri> o algunas otras clases).</span><span class="sxs-lookup"><span data-stu-id="0959a-158">Deserializing the empty buffer (new byte[0]) into <xref:System.Object> (or <xref:System.Uri>, or some other classes).</span></span>|<span data-ttu-id="0959a-159">SerializationException</span><span class="sxs-lookup"><span data-stu-id="0959a-159">SerializationException</span></span>|<span data-ttu-id="0959a-160">nulo</span><span class="sxs-lookup"><span data-stu-id="0959a-160">null</span></span>|
|<span data-ttu-id="0959a-161">Serialización de <xref:System.DBNull.Value></span><span class="sxs-lookup"><span data-stu-id="0959a-161">Serialization of <xref:System.DBNull.Value></span></span>|<span data-ttu-id="0959a-162">{} (o {"__type": "#System"})</span><span class="sxs-lookup"><span data-stu-id="0959a-162">{} (or {"__type":"#System"})</span></span>|<span data-ttu-id="0959a-163">Null</span><span class="sxs-lookup"><span data-stu-id="0959a-163">Null</span></span>|
|<span data-ttu-id="0959a-164">Serialización de los miembros privados de tipos [Serializable].</span><span class="sxs-lookup"><span data-stu-id="0959a-164">Serialization of the private members of [Serializable] types.</span></span>|<span data-ttu-id="0959a-165">serialized</span><span class="sxs-lookup"><span data-stu-id="0959a-165">serialized</span></span>|<span data-ttu-id="0959a-166">not serialized</span><span class="sxs-lookup"><span data-stu-id="0959a-166">not serialized</span></span>|
|<span data-ttu-id="0959a-167">Serialización de las propiedades públicas de los tipos <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="0959a-167">Serialization of the public properties of <xref:System.Runtime.Serialization.ISerializable> types.</span></span>|<span data-ttu-id="0959a-168">not serialized</span><span class="sxs-lookup"><span data-stu-id="0959a-168">not serialized</span></span>|<span data-ttu-id="0959a-169">serialized</span><span class="sxs-lookup"><span data-stu-id="0959a-169">serialized</span></span>|
|<span data-ttu-id="0959a-170">"Extensiones" de JSON</span><span class="sxs-lookup"><span data-stu-id="0959a-170">"Extensions" of JSON</span></span>|<span data-ttu-id="0959a-171">Conforme con la especificación de JSON, que requiere comillas en los nombres de miembro de objetos ({"a":"hola"}).</span><span class="sxs-lookup"><span data-stu-id="0959a-171">Adheres to the JSON specification, which requires quotes on object member names ({"a":"hello"}).</span></span>|<span data-ttu-id="0959a-172">Admite los nombres de miembros de objeto sin comillas ({a:"hola"}).</span><span class="sxs-lookup"><span data-stu-id="0959a-172">Supports the names of object members without quotes ({a:"hello"}).</span></span>|
|<span data-ttu-id="0959a-173"><xref:System.DateTime>Hora universal coordinada (UTC)</span><span class="sxs-lookup"><span data-stu-id="0959a-173"><xref:System.DateTime> Coordinated Universal Time (UTC)</span></span>|<span data-ttu-id="0959a-174">No es compatible con el formato "\\/Date(123456789U)\\/" o "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".</span><span class="sxs-lookup"><span data-stu-id="0959a-174">Does not support format "\\/Date(123456789U)\\/" or "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)".</span></span>|<span data-ttu-id="0959a-175">Admite el formato "\\/Date(123456789U)\\/" y "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "como valores de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="0959a-175">Supports format "\\/Date(123456789U)\\/" and "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)" as DateTime values.</span></span>|
|<span data-ttu-id="0959a-176">Representación de diccionarios</span><span class="sxs-lookup"><span data-stu-id="0959a-176">Representation of dictionaries</span></span>|<span data-ttu-id="0959a-177">Una matriz de KeyValuePair\<K, V >, administra tipos clave que no son cadenas.</span><span class="sxs-lookup"><span data-stu-id="0959a-177">An array of KeyValuePair\<K,V>, handles key types that are not strings.</span></span>|<span data-ttu-id="0959a-178">Como objetos JSON reales, pero solo controla los tipos clave que son cadenas.</span><span class="sxs-lookup"><span data-stu-id="0959a-178">As actual JSON objects - but only handles key types that are strings.</span></span>|
|<span data-ttu-id="0959a-179">Caracteres con escape</span><span class="sxs-lookup"><span data-stu-id="0959a-179">Escaped characters</span></span>|<span data-ttu-id="0959a-180">Siempre con una barra diagonal de escape (/); nunca permite caracteres de JSON no válidos sin escape, como "\n".</span><span class="sxs-lookup"><span data-stu-id="0959a-180">Always with an escape forward slash (/); never allows un-escaped invalid JSON characters, such as "\n".</span></span>|<span data-ttu-id="0959a-181">Con una barra diagonal de escape (/) para los valores DateTime .</span><span class="sxs-lookup"><span data-stu-id="0959a-181">With an escape forward slash (/) for DateTime values.</span></span>|

## <a name="see-also"></a><span data-ttu-id="0959a-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="0959a-182">See also</span></span>

- [<span data-ttu-id="0959a-183">Cómo: Usar la configuración para agregar un extremo de AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0959a-183">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
