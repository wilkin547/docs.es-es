---
title: Formateador de operación y selector de operación
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: 9d1bc0afa54f89e064eab3f3e45da60c8d10de38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144284"
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="089da-102">Formateador de operación y selector de operación</span><span class="sxs-lookup"><span data-stu-id="089da-102">Operation Formatter and Operation Selector</span></span>
<span data-ttu-id="089da-103">En este ejemplo se muestra cómo se pueden usar los puntos de extensibilidad de Windows Communication Foundation (WCF) para permitir datos de mensaje en un formato diferente de lo que WCF espera.</span><span class="sxs-lookup"><span data-stu-id="089da-103">This sample demonstrates how Windows Communication Foundation (WCF) extensibility points can be used to allow message data in a different format from what WCF expects.</span></span> <span data-ttu-id="089da-104">De forma predeterminada, los formateadores de `soap:body` WCF esperan que los parámetros del método se incluyan en el elemento.</span><span class="sxs-lookup"><span data-stu-id="089da-104">By default, WCF formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="089da-105">El ejemplo muestra cómo implementar un formateador de operación personalizado que analiza los datos de parámetro a partir de una cadena de consulta HTTP GET en su lugar e invoca los métodos que utilizan esos datos.</span><span class="sxs-lookup"><span data-stu-id="089da-105">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="089da-106">El ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="089da-106">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="089da-107">Muestra cómo se pueden cambiar los mensajes de suma, resta, multiplicación y división para usar HTTP GET para las solicitudes de cliente a servidor y HTTP POST con mensajes POX para respuestas de servidor a cliente.</span><span class="sxs-lookup"><span data-stu-id="089da-107">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="089da-108">Para ello, el ejemplo proporciona lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="089da-108">To do so, the sample provides the following:</span></span>  
  
- <span data-ttu-id="089da-109">`QueryStringFormatter`, que implementa <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> y <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> para el cliente y el servidor, respectivamente, y procesa los datos en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="089da-109">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
- <span data-ttu-id="089da-110">`UriOperationSelector`, que implementa <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> en el servidor para realizar el envío de la operación según el nombre de la operación en la solicitud GET.</span><span class="sxs-lookup"><span data-stu-id="089da-110">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
- <span data-ttu-id="089da-111">Comportamiento del extremo `EnableHttpGetRequestsBehavior` (y la configuración correspondiente), que agrega el selector de operación necesario al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="089da-111">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
- <span data-ttu-id="089da-112">Muestra cómo insertar un nuevo formateador de operación en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="089da-112">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
- <span data-ttu-id="089da-113">En este ejemplo, el cliente y el servicio son aplicaciones de consola (.exe).</span><span class="sxs-lookup"><span data-stu-id="089da-113">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="089da-114">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="089da-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="089da-115">Conceptos clave</span><span class="sxs-lookup"><span data-stu-id="089da-115">Key Concepts</span></span>  
 <span data-ttu-id="089da-116">`QueryStringFormatter`- El formateador de operaciones es el componente de WCF que es responsable de convertir un mensaje en una matriz de objetos de parámetro y una matriz de objetos de parámetro en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="089da-116">`QueryStringFormatter` - The operation formatter is the component in WCF that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="089da-117">Esto se hace en el cliente utilizando la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> y en el servidor con la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>.</span><span class="sxs-lookup"><span data-stu-id="089da-117">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="089da-118">Estas interfaces le permiten a los usuarios recibir los mensajes de respuesta y solicitud desde los métodos `Serialize` y `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="089da-118">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="089da-119">En este ejemplo, `QueryStringFormatter` implementa ambas interfaces y se implementa en el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="089da-119">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="089da-120">Solicitud:</span><span class="sxs-lookup"><span data-stu-id="089da-120">Request:</span></span>  
  
- <span data-ttu-id="089da-121">El ejemplo utiliza la clase <xref:System.ComponentModel.TypeConverter> para convertir los datos de parámetro en el mensaje de solicitud en cadenas y viceversa.</span><span class="sxs-lookup"><span data-stu-id="089da-121">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="089da-122">Si <xref:System.ComponentModel.TypeConverter> no está disponible para un tipo específico, el formateador del ejemplo produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="089da-122">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
- <span data-ttu-id="089da-123">En el método `IClientMessageFormatter.SerializeRequest` en el cliente, el formateador crea un URI con la dirección A adecuada y añade el nombre de la operación como un sufijo.</span><span class="sxs-lookup"><span data-stu-id="089da-123">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="089da-124">Este nombre se utiliza para enviar a la operación adecuada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="089da-124">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="089da-125">Toma a continuación la matriz de objetos de parámetro y serializa los datos de parámetro en la cadena de consulta del URI utilizando nombres de parámetro y los valores convertidos por la clase <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="089da-125">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="089da-126">Las propiedades <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> y <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> se establecen en este URI.</span><span class="sxs-lookup"><span data-stu-id="089da-126">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="089da-127">Se tiene acceso a <xref:System.ServiceModel.Channels.MessageProperties> mediante la propiedad <xref:System.ServiceModel.Channels.Message.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="089da-127"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
- <span data-ttu-id="089da-128">En el método `IDispatchMessageFormatter.DeserializeRequest` en el servidor, el formateador recupera el URI `Via` en las propiedades del mensaje de solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="089da-128">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="089da-129">Analiza los pares nombre-valor en la cadena de consulta del URI en nombres y valores de parámetro y los utiliza para rellenar la matriz de parámetros que se ha pasado en el método.</span><span class="sxs-lookup"><span data-stu-id="089da-129">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="089da-130">Tenga en cuenta que el envío de la operación ya se ha producido, por lo que el sufijo del nombre de la operación se omite en este método.</span><span class="sxs-lookup"><span data-stu-id="089da-130">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="089da-131">Respuesta:</span><span class="sxs-lookup"><span data-stu-id="089da-131">Response:</span></span>  
  
- <span data-ttu-id="089da-132">En este ejemplo, solo se utiliza HTTP GET para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="089da-132">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="089da-133">El formateador delega el envío de la respuesta al formateador original que se habría utilizado para generar un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="089da-133">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="089da-134">Uno de los objetivos de este ejemplo es mostrar cómo se puede implementar este tipo de formateador que delega.</span><span class="sxs-lookup"><span data-stu-id="089da-134">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="089da-135">Clase UriPathSuffixOperationSelector</span><span class="sxs-lookup"><span data-stu-id="089da-135">UriPathSuffixOperationSelector Class</span></span>  
 <span data-ttu-id="089da-136">La interfaz <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> permite a los usuarios implementar su propia lógica para la que la operación de un mensaje particular debería enviarse.</span><span class="sxs-lookup"><span data-stu-id="089da-136">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="089da-137">En este ejemplo, se debe implementar `UriPathSuffixOperationSelector` en el servidor para seleccionar la operación adecuada porque el nombre de la operación está incluido en el URI de HTTP GET en lugar de en un encabezado de acción en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="089da-137">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="089da-138">El ejemplo se configura para permitir solo nombres de operación sin distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="089da-138">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="089da-139">El método `SelectOperation` toma el mensaje entrante y busca el URI de `Via` en sus propiedades de mensaje.</span><span class="sxs-lookup"><span data-stu-id="089da-139">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="089da-140">Extrae el sufijo del nombre de operación del URI, busca una tabla interna para obtener el nombre de la operación al que se debería enviar el mensaje y devuelve ese nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="089da-140">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="089da-141">Clase EnableHttpGetRequestsBehavior</span><span class="sxs-lookup"><span data-stu-id="089da-141">EnableHttpGetRequestsBehavior Class</span></span>  
 <span data-ttu-id="089da-142">Se puede configurar el componente `UriPathSuffixOperationSelector` mediante programación o a través de un comportamiento del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="089da-142">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="089da-143">El ejemplo implementa el comportamiento `EnableHttpGetRequestsBehavior`, que se especifica en el archivo de configuración de la aplicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="089da-143">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="089da-144">En el servidor:</span><span class="sxs-lookup"><span data-stu-id="089da-144">On the server:</span></span>  
  
 <span data-ttu-id="089da-145"><xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> está establecido en la implementación <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="089da-145">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="089da-146">De forma predeterminada, WCF usa un filtro de dirección de coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="089da-146">By default, WCF uses an exact-match address filter.</span></span> <span data-ttu-id="089da-147">El URI en el mensaje entrante contiene un sufijo de nombre de operación seguido por una cadena de consulta que contiene los datos de parámetro, por lo que el comportamiento del extremo también cambia el filtro de la dirección para ser un filtro de coincidencia de prefijo.</span><span class="sxs-lookup"><span data-stu-id="089da-147">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="089da-148">Usa el<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> WCF para este propósito.</span><span class="sxs-lookup"><span data-stu-id="089da-148">It uses the WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="089da-149">Instalación de los formateadores de operación</span><span class="sxs-lookup"><span data-stu-id="089da-149">Installing operation formatters</span></span>  
 <span data-ttu-id="089da-150">Los comportamientos de la operación que especifican los formateadores son únicos.</span><span class="sxs-lookup"><span data-stu-id="089da-150">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="089da-151">Dicho comportamiento se implementa siempre de forma predeterminada en cada operación para crear el formateador de operación necesario.</span><span class="sxs-lookup"><span data-stu-id="089da-151">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="089da-152">Sin embargo, estos comportamientos se parecen a otro comportamiento de la operación; ningún otro atributo los puede identificar.</span><span class="sxs-lookup"><span data-stu-id="089da-152">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="089da-153">Para instalar un comportamiento de reemplazo, la implementación debe buscar comportamientos de formateador específicos que se instalan por el cargador de tipos WCF de forma predeterminada y reemplazarlo o agregar un comportamiento compatible para ejecutarse después del comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="089da-153">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the WCF type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="089da-154">Se pueden configurar estos comportamientos de formateadores de operación mediante programación antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> o especificando un comportamiento de la operación que se ejecuta después del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="089da-154">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="089da-155">Sin embargo, un comportamiento del extremo (y por consiguiente por configuración) no puede configurarse con facilidad, porque el modelo de comportamiento no permite que un comportamiento sustituya a otros comportamientos o que modifique el árbol de descripción.</span><span class="sxs-lookup"><span data-stu-id="089da-155">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="089da-156">En el cliente:</span><span class="sxs-lookup"><span data-stu-id="089da-156">On the client:</span></span>  
  
 <span data-ttu-id="089da-157">Se debe implementar la implementación <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> para que pueda convertir las solicitudes en las solicitudes en solicitudes HTTP GET y delegar al formateador original para las respuestas.</span><span class="sxs-lookup"><span data-stu-id="089da-157">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="089da-158">Esto se hace llamando al método del asistente `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`.</span><span class="sxs-lookup"><span data-stu-id="089da-158">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="089da-159">Este paso se debe realizar antes de llamar a `CreateChannel`.</span><span class="sxs-lookup"><span data-stu-id="089da-159">This must be done before calling `CreateChannel`.</span></span>  
  
```csharp  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 <span data-ttu-id="089da-160">En el servidor:</span><span class="sxs-lookup"><span data-stu-id="089da-160">On the server:</span></span>  
  
- <span data-ttu-id="089da-161">Se debe implementar la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> para que pueda leer las solicitudes HTTP GET y delegar en el formateador original para escribir las respuestas.</span><span class="sxs-lookup"><span data-stu-id="089da-161">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="089da-162">Esto se hace llamando al mismo método del asistente `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` como el cliente (vea el ejemplo de código anterior).</span><span class="sxs-lookup"><span data-stu-id="089da-162">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
- <span data-ttu-id="089da-163">Este paso se debe realizar antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="089da-163">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="089da-164">En este ejemplo, mostramos cómo el formateador se modifica manualmente antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="089da-164">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="089da-165">Otra manera de lograr lo mismo es derivar una clase de <xref:System.ServiceModel.ServiceHost> que realiza las llamadas a `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` antes de abrirse (para ver ejemplos consulte la documentación sobre hospedaje y los ejemplos).</span><span class="sxs-lookup"><span data-stu-id="089da-165">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="089da-166">Experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="089da-166">User experience</span></span>  
 <span data-ttu-id="089da-167">En el servidor:</span><span class="sxs-lookup"><span data-stu-id="089da-167">On the server:</span></span>  
  
- <span data-ttu-id="089da-168">La implementación del servidor `ICalculator` no tiene que cambiarse.</span><span class="sxs-lookup"><span data-stu-id="089da-168">The server `ICalculator` implementation does not need to change.</span></span>  
  
- <span data-ttu-id="089da-169">App.config para el servicio debe utilizar un enlace POX personalizado que defina el atributo `messageVersion` del elemento `textMessageEncoding` en `None`.</span><span class="sxs-lookup"><span data-stu-id="089da-169">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="089da-170">App.config para el servicio también debe especificar el `EnableHttpGetRequestsBehavior` personalizado agregándolo a la sección de extensiones de comportamiento y utilizándolo.</span><span class="sxs-lookup"><span data-stu-id="089da-170">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
- <span data-ttu-id="089da-171">Agregue los formateadores de operación antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="089da-171">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="089da-172">En el cliente:</span><span class="sxs-lookup"><span data-stu-id="089da-172">On the client:</span></span>  
  
- <span data-ttu-id="089da-173">La implementación del cliente no tiene que cambiar.</span><span class="sxs-lookup"><span data-stu-id="089da-173">The client implementation does not need to change.</span></span>  
  
- <span data-ttu-id="089da-174">App.config para el cliente debe utilizar un enlace POX personalizado que define el atributo `messageVersion` del elemento `textMessageEncoding` en `None`.</span><span class="sxs-lookup"><span data-stu-id="089da-174">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="089da-175">Una diferencia del servicio es que el cliente debe habilitar el direccionamiento manual para que se pueda modificar la dirección A saliente.</span><span class="sxs-lookup"><span data-stu-id="089da-175">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="089da-176">App.config para el cliente debe especificar el mismo `EnableHttpGetRequestsBehavior` personalizado que el servidor.</span><span class="sxs-lookup"><span data-stu-id="089da-176">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
- <span data-ttu-id="089da-177">Agregue los formateadores de operación antes de llamar a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span><span class="sxs-lookup"><span data-stu-id="089da-177">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="089da-178">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="089da-178">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="089da-179">Las cuatro operaciones (sumar, restar, multiplicar y dividir) deberán realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="089da-179">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="089da-180">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="089da-180">The samples may already be installed on your machine.</span></span> <span data-ttu-id="089da-181">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="089da-181">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="089da-182">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="089da-182">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="089da-183">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="089da-183">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="089da-184">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="089da-184">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="089da-185">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="089da-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="089da-186">Para compilar la solución, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="089da-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="089da-187">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="089da-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
