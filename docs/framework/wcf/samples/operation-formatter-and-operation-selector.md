---
description: 'Más información acerca de: formateador de operaciones y selector de operaciones'
title: Formateador de operación y selector de operación
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: dedfa92ddd2f8192eef6b11d8ecde133b961d6cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793225"
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="58e31-103">Formateador de operación y selector de operación</span><span class="sxs-lookup"><span data-stu-id="58e31-103">Operation Formatter and Operation Selector</span></span>

<span data-ttu-id="58e31-104">Este ejemplo muestra cómo se pueden usar los puntos de extensibilidad de Windows Communication Foundation (WCF) para permitir datos de mensaje en un formato diferente del que espera WCF.</span><span class="sxs-lookup"><span data-stu-id="58e31-104">This sample demonstrates how Windows Communication Foundation (WCF) extensibility points can be used to allow message data in a different format from what WCF expects.</span></span> <span data-ttu-id="58e31-105">De forma predeterminada, los formateadores de WCF esperan que los parámetros de método se incluyan en el `soap:body` elemento.</span><span class="sxs-lookup"><span data-stu-id="58e31-105">By default, WCF formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="58e31-106">El ejemplo muestra cómo implementar un formateador de operación personalizado que analiza los datos de parámetro a partir de una cadena de consulta HTTP GET en su lugar e invoca los métodos que utilizan esos datos.</span><span class="sxs-lookup"><span data-stu-id="58e31-106">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="58e31-107">El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="58e31-107">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="58e31-108">Muestra cómo se pueden cambiar los mensajes de suma, resta, multiplicación y división para usar HTTP GET para las solicitudes de cliente a servidor y HTTP POST con mensajes POX para respuestas de servidor a cliente.</span><span class="sxs-lookup"><span data-stu-id="58e31-108">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="58e31-109">Para ello, el ejemplo proporciona lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e31-109">To do so, the sample provides the following:</span></span>  
  
- <span data-ttu-id="58e31-110">`QueryStringFormatter`, que implementa <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> y <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> para el cliente y el servidor, respectivamente, y procesa los datos en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="58e31-110">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
- <span data-ttu-id="58e31-111">`UriOperationSelector`, que implementa <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> en el servidor para realizar el envío de la operación según el nombre de la operación en la solicitud GET.</span><span class="sxs-lookup"><span data-stu-id="58e31-111">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
- <span data-ttu-id="58e31-112">Comportamiento del extremo `EnableHttpGetRequestsBehavior` (y la configuración correspondiente), que agrega el selector de operación necesario al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="58e31-112">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
- <span data-ttu-id="58e31-113">Muestra cómo insertar un nuevo formateador de operación en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="58e31-113">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
- <span data-ttu-id="58e31-114">En este ejemplo, el cliente y el servicio son aplicaciones de consola (.exe).</span><span class="sxs-lookup"><span data-stu-id="58e31-114">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58e31-115">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="58e31-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="58e31-116">Conceptos clave</span><span class="sxs-lookup"><span data-stu-id="58e31-116">Key Concepts</span></span>  

 <span data-ttu-id="58e31-117">`QueryStringFormatter` -El formateador de la operación es el componente de WCF responsable de convertir un mensaje en una matriz de objetos de parámetro y una matriz de objetos de parámetro en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="58e31-117">`QueryStringFormatter` - The operation formatter is the component in WCF that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="58e31-118">Esto se hace en el cliente utilizando la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> y en el servidor con la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>.</span><span class="sxs-lookup"><span data-stu-id="58e31-118">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="58e31-119">Estas interfaces le permiten a los usuarios recibir los mensajes de respuesta y solicitud desde los métodos `Serialize` y `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="58e31-119">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="58e31-120">En este ejemplo, `QueryStringFormatter` implementa ambas interfaces y se implementa en el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="58e31-120">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="58e31-121">Solicitud:</span><span class="sxs-lookup"><span data-stu-id="58e31-121">Request:</span></span>  
  
- <span data-ttu-id="58e31-122">El ejemplo utiliza la clase <xref:System.ComponentModel.TypeConverter> para convertir los datos de parámetro en el mensaje de solicitud en cadenas y viceversa.</span><span class="sxs-lookup"><span data-stu-id="58e31-122">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="58e31-123">Si <xref:System.ComponentModel.TypeConverter> no está disponible para un tipo específico, el formateador del ejemplo produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="58e31-123">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
- <span data-ttu-id="58e31-124">En el método `IClientMessageFormatter.SerializeRequest` en el cliente, el formateador crea un URI con la dirección A adecuada y añade el nombre de la operación como un sufijo.</span><span class="sxs-lookup"><span data-stu-id="58e31-124">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="58e31-125">Este nombre se utiliza para enviar a la operación adecuada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="58e31-125">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="58e31-126">Toma a continuación la matriz de objetos de parámetro y serializa los datos de parámetro en la cadena de consulta del URI utilizando nombres de parámetro y los valores convertidos por la clase <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="58e31-126">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="58e31-127">Las propiedades <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> y <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> se establecen en este URI.</span><span class="sxs-lookup"><span data-stu-id="58e31-127">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="58e31-128">Se tiene acceso a <xref:System.ServiceModel.Channels.MessageProperties> mediante la propiedad <xref:System.ServiceModel.Channels.Message.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="58e31-128"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
- <span data-ttu-id="58e31-129">En el método `IDispatchMessageFormatter.DeserializeRequest` en el servidor, el formateador recupera el URI `Via` en las propiedades del mensaje de solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="58e31-129">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="58e31-130">Analiza los pares nombre-valor en la cadena de consulta del URI en nombres y valores de parámetro y los utiliza para rellenar la matriz de parámetros que se ha pasado en el método.</span><span class="sxs-lookup"><span data-stu-id="58e31-130">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="58e31-131">Tenga en cuenta que el envío de la operación ya se ha producido, por lo que el sufijo del nombre de la operación se omite en este método.</span><span class="sxs-lookup"><span data-stu-id="58e31-131">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="58e31-132">Respuesta:</span><span class="sxs-lookup"><span data-stu-id="58e31-132">Response:</span></span>  
  
- <span data-ttu-id="58e31-133">En este ejemplo, solo se utiliza HTTP GET para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="58e31-133">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="58e31-134">El formateador delega el envío de la respuesta al formateador original que se habría utilizado para generar un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="58e31-134">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="58e31-135">Uno de los objetivos de este ejemplo es mostrar cómo se puede implementar este tipo de formateador que delega.</span><span class="sxs-lookup"><span data-stu-id="58e31-135">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="58e31-136">Clase UriPathSuffixOperationSelector</span><span class="sxs-lookup"><span data-stu-id="58e31-136">UriPathSuffixOperationSelector Class</span></span>  

 <span data-ttu-id="58e31-137">La interfaz <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> permite a los usuarios implementar su propia lógica para la que la operación de un mensaje particular debería enviarse.</span><span class="sxs-lookup"><span data-stu-id="58e31-137">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="58e31-138">En este ejemplo, se debe implementar `UriPathSuffixOperationSelector` en el servidor para seleccionar la operación adecuada porque el nombre de la operación está incluido en el URI de HTTP GET en lugar de en un encabezado de acción en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="58e31-138">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="58e31-139">El ejemplo se configura para permitir solo nombres de operación sin distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="58e31-139">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="58e31-140">El método `SelectOperation` toma el mensaje entrante y busca el URI de `Via` en sus propiedades de mensaje.</span><span class="sxs-lookup"><span data-stu-id="58e31-140">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="58e31-141">Extrae el sufijo del nombre de operación del URI, busca una tabla interna para obtener el nombre de la operación al que se debería enviar el mensaje y devuelve ese nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="58e31-141">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="58e31-142">Clase EnableHttpGetRequestsBehavior</span><span class="sxs-lookup"><span data-stu-id="58e31-142">EnableHttpGetRequestsBehavior Class</span></span>  

 <span data-ttu-id="58e31-143">Se puede configurar el componente `UriPathSuffixOperationSelector` mediante programación o a través de un comportamiento del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="58e31-143">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="58e31-144">El ejemplo implementa el comportamiento `EnableHttpGetRequestsBehavior`, que se especifica en el archivo de configuración de la aplicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="58e31-144">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="58e31-145">En el servidor:</span><span class="sxs-lookup"><span data-stu-id="58e31-145">On the server:</span></span>  
  
 <span data-ttu-id="58e31-146"><xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> está establecido en la implementación <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="58e31-146">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="58e31-147">De forma predeterminada, WCF usa un filtro de direcciones de coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="58e31-147">By default, WCF uses an exact-match address filter.</span></span> <span data-ttu-id="58e31-148">El URI en el mensaje entrante contiene un sufijo de nombre de operación seguido por una cadena de consulta que contiene los datos de parámetro, por lo que el comportamiento del extremo también cambia el filtro de la dirección para ser un filtro de coincidencia de prefijo.</span><span class="sxs-lookup"><span data-stu-id="58e31-148">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="58e31-149">Usa WCF <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> para este propósito.</span><span class="sxs-lookup"><span data-stu-id="58e31-149">It uses the WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="58e31-150">Instalación de los formateadores de operación</span><span class="sxs-lookup"><span data-stu-id="58e31-150">Installing operation formatters</span></span>  

 <span data-ttu-id="58e31-151">Los comportamientos de la operación que especifican los formateadores son únicos.</span><span class="sxs-lookup"><span data-stu-id="58e31-151">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="58e31-152">Dicho comportamiento se implementa siempre de forma predeterminada en cada operación para crear el formateador de operación necesario.</span><span class="sxs-lookup"><span data-stu-id="58e31-152">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="58e31-153">Sin embargo, estos comportamientos se parecen a otro comportamiento de la operación; ningún otro atributo los puede identificar.</span><span class="sxs-lookup"><span data-stu-id="58e31-153">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="58e31-154">Para instalar un comportamiento de reemplazo, la implementación debe buscar comportamientos de formateador específicos que se instalan de forma predeterminada en el cargador de tipos de WCF y reemplazarlos o agregar un comportamiento compatible para que se ejecute después del comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="58e31-154">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the WCF type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="58e31-155">Se pueden configurar estos comportamientos de formateadores de operación mediante programación antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> o especificando un comportamiento de la operación que se ejecuta después del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="58e31-155">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="58e31-156">Sin embargo, un comportamiento del extremo (y por consiguiente por configuración) no puede configurarse con facilidad, porque el modelo de comportamiento no permite que un comportamiento sustituya a otros comportamientos o que modifique el árbol de descripción.</span><span class="sxs-lookup"><span data-stu-id="58e31-156">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="58e31-157">En el cliente:</span><span class="sxs-lookup"><span data-stu-id="58e31-157">On the client:</span></span>  
  
 <span data-ttu-id="58e31-158">Se debe implementar la implementación <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> para que pueda convertir las solicitudes en las solicitudes en solicitudes HTTP GET y delegar al formateador original para las respuestas.</span><span class="sxs-lookup"><span data-stu-id="58e31-158">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="58e31-159">Esto se hace llamando al método del asistente `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`.</span><span class="sxs-lookup"><span data-stu-id="58e31-159">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="58e31-160">Este paso se debe realizar antes de llamar a `CreateChannel`.</span><span class="sxs-lookup"><span data-stu-id="58e31-160">This must be done before calling `CreateChannel`.</span></span>  
  
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
  
 <span data-ttu-id="58e31-161">En el servidor:</span><span class="sxs-lookup"><span data-stu-id="58e31-161">On the server:</span></span>  
  
- <span data-ttu-id="58e31-162">Se debe implementar la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> para que pueda leer las solicitudes HTTP GET y delegar en el formateador original para escribir las respuestas.</span><span class="sxs-lookup"><span data-stu-id="58e31-162">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="58e31-163">Esto se hace llamando al mismo método del asistente `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` como el cliente (vea el ejemplo de código anterior).</span><span class="sxs-lookup"><span data-stu-id="58e31-163">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
- <span data-ttu-id="58e31-164">Este paso se debe realizar antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="58e31-164">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="58e31-165">En este ejemplo, mostramos cómo el formateador se modifica manualmente antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="58e31-165">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="58e31-166">Otra manera de lograr lo mismo es derivar una clase de <xref:System.ServiceModel.ServiceHost> que realiza las llamadas a `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` antes de abrirse (para ver ejemplos consulte la documentación sobre hospedaje y los ejemplos).</span><span class="sxs-lookup"><span data-stu-id="58e31-166">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="58e31-167">Experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="58e31-167">User experience</span></span>  

 <span data-ttu-id="58e31-168">En el servidor:</span><span class="sxs-lookup"><span data-stu-id="58e31-168">On the server:</span></span>  
  
- <span data-ttu-id="58e31-169">La implementación del servidor `ICalculator` no tiene que cambiarse.</span><span class="sxs-lookup"><span data-stu-id="58e31-169">The server `ICalculator` implementation does not need to change.</span></span>  
  
- <span data-ttu-id="58e31-170">App.config para el servicio debe utilizar un enlace POX personalizado que defina el atributo `messageVersion` del elemento `textMessageEncoding` en `None`.</span><span class="sxs-lookup"><span data-stu-id="58e31-170">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
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
  
- <span data-ttu-id="58e31-171">App.config para el servicio también debe especificar el `EnableHttpGetRequestsBehavior` personalizado agregándolo a la sección de extensiones de comportamiento y utilizándolo.</span><span class="sxs-lookup"><span data-stu-id="58e31-171">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
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
  
- <span data-ttu-id="58e31-172">Agregue los formateadores de operación antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="58e31-172">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="58e31-173">En el cliente:</span><span class="sxs-lookup"><span data-stu-id="58e31-173">On the client:</span></span>  
  
- <span data-ttu-id="58e31-174">La implementación del cliente no tiene que cambiar.</span><span class="sxs-lookup"><span data-stu-id="58e31-174">The client implementation does not need to change.</span></span>  
  
- <span data-ttu-id="58e31-175">App.config para el cliente debe utilizar un enlace POX personalizado que define el atributo `messageVersion` del elemento `textMessageEncoding` en `None`.</span><span class="sxs-lookup"><span data-stu-id="58e31-175">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="58e31-176">Una diferencia del servicio es que el cliente debe habilitar el direccionamiento manual para que se pueda modificar la dirección A saliente.</span><span class="sxs-lookup"><span data-stu-id="58e31-176">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
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
  
- <span data-ttu-id="58e31-177">App.config para el cliente debe especificar el mismo `EnableHttpGetRequestsBehavior` personalizado que el servidor.</span><span class="sxs-lookup"><span data-stu-id="58e31-177">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
- <span data-ttu-id="58e31-178">Agregue los formateadores de operación antes de llamar a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span><span class="sxs-lookup"><span data-stu-id="58e31-178">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="58e31-179">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="58e31-179">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="58e31-180">Las cuatro operaciones (sumar, restar, multiplicar y dividir) deberán realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="58e31-180">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="58e31-181">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="58e31-181">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58e31-182">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="58e31-182">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="58e31-183">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="58e31-183">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58e31-184">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="58e31-184">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="58e31-185">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="58e31-185">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="58e31-186">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58e31-186">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="58e31-187">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58e31-187">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="58e31-188">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58e31-188">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
