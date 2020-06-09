---
title: Distribución mediante el elemento del cuerpo
ms.date: 03/30/2017
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
ms.openlocfilehash: 19913cdaa47d766f62a313e216a653ac69633a99
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594704"
---
# <a name="dispatch-by-body-element"></a><span data-ttu-id="2cd80-102">Distribución mediante el elemento del cuerpo</span><span class="sxs-lookup"><span data-stu-id="2cd80-102">Dispatch by Body Element</span></span>
<span data-ttu-id="2cd80-103">Este ejemplo muestra cómo implementar un algoritmo alternativo para asignar mensajes entrantes a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="2cd80-103">This sample demonstrates how to implement an alternate algorithm for assigning incoming messages to operations.</span></span>  
  
 <span data-ttu-id="2cd80-104">De forma predeterminada, el servicio del distribuidor ejemplar selecciona el método de control adecuado para un mensaje entrante basado en el encabezamiento “Acción” del direccionamiento del WS del mensaje o la información equivalente en la solicitud SOAP del Http.</span><span class="sxs-lookup"><span data-stu-id="2cd80-104">By default, the service model dispatcher selects the appropriate handling method for an incoming message based on the message's WS-Addressing "Action" header or the equivalent information in the HTTP SOAP request.</span></span>  
  
 <span data-ttu-id="2cd80-105">Algunas pilas de servicios Web del SOAP 1.1 que no siguen las instrucciones del WS-I Basic Profile 1.1 no envían mensajes basados en el URI Acción, sino basados en el nombre completo de XML del primer elemento dentro del cuerpo de SOAP.</span><span class="sxs-lookup"><span data-stu-id="2cd80-105">Some SOAP 1.1 Web services stacks that do not follow the WS-I Basic Profile 1.1 guidelines do not dispatch messages based on the Action URI, but rather based on the XML qualified name of the first element inside the SOAP body.</span></span> <span data-ttu-id="2cd80-106">Igualmente, la parte del cliente de estas pilas podría enviar los mensajes con un encabezado de Http SoapAction vacío o arbitrario, el cual se permitió por la especificación SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="2cd80-106">Likewise, the client side of these stacks might send messages with an empty or arbitrary HTTP SoapAction header, which was permitted by the SOAP 1.1 specification.</span></span>  
  
 <span data-ttu-id="2cd80-107">Para cambiar la manera en la cual se envían los mensajes a los métodos, el ejemplo implementa la interfaz de extensibilidad <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> en `DispatchByBodyElementOperationSelector`.</span><span class="sxs-lookup"><span data-stu-id="2cd80-107">To change the way messages are dispatched to methods, the sample implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> extensibility interface on the `DispatchByBodyElementOperationSelector`.</span></span> <span data-ttu-id="2cd80-108">Esta clase selecciona operaciones basadas en el primer elemento del cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2cd80-108">This class selects operations based on the first element of the message body.</span></span>  
  
 <span data-ttu-id="2cd80-109">El constructor de clase espera un diccionario lleno con pares de `XmlQualifiedName` y cadenas, con los que los nombres completos indiquen el nombre del primer elemento secundario del cuerpo de SOAP y que las cadenas indiquen el nombre de la operación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2cd80-109">The class constructor expects a dictionary populated with pairs of `XmlQualifiedName` and strings, whereby the qualified names indicate the name of the first child of the SOAP body and the strings indicate the matching operation name.</span></span> <span data-ttu-id="2cd80-110">`defaultOperationName` es el nombre de la operación que recibe todos los mensajes que no pueden coincidir contra este diccionario:</span><span class="sxs-lookup"><span data-stu-id="2cd80-110">The `defaultOperationName` is the name of the operation that receives all messages that cannot be matched against this dictionary:</span></span>  
  
```csharp
class DispatchByBodyElementOperationSelector : IDispatchOperationSelector  
{  
    Dictionary<XmlQualifiedName, string> dispatchDictionary;  
    string defaultOperationName;  
  
    public DispatchByBodyElementOperationSelector(Dictionary<XmlQualifiedName,string> dispatchDictionary, string defaultOperationName)  
    {  
        this.dispatchDictionary = dispatchDictionary;  
        this.defaultOperationName = defaultOperationName;  
    }  
}
```  
  
 <span data-ttu-id="2cd80-111">Las implementaciones de <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> son muy sencillas de generar ya que solo existe un método en la interfaz: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cd80-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementations are very straightforward to build as there is only one method on the interface: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span></span> <span data-ttu-id="2cd80-112">El trabajo de este método es inspeccionar un mensaje entrante y devolver una cadena que iguala el nombre de un método en el contrato de servicios para el extremo actual.</span><span class="sxs-lookup"><span data-stu-id="2cd80-112">The job of this method is to inspect an incoming message and to return a string that equals the name of a method on the service contract for the current endpoint.</span></span>  
  
 <span data-ttu-id="2cd80-113">En este ejemplo, el selector de la operación adquiere <xref:System.Xml.XmlDictionaryReader> para el cuerpo del mensaje entrante utilizando <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cd80-113">In this sample, the operation selector acquires an <xref:System.Xml.XmlDictionaryReader> for the incoming message's body using <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span></span> <span data-ttu-id="2cd80-114">Este método ya coloca al lector en el primer elemento secundario del cuerpo del mensaje para que sea suficiente obtener el nombre del elemento vigente y el espacio de nombres URI y combinarlos en `XmlQualifiedName` que se utiliza a continuación para buscar la operación correspondiente del diccionario contenida por el selector de la operación.</span><span class="sxs-lookup"><span data-stu-id="2cd80-114">This method already positions the reader on the first child of the message's body so that it is sufficient to get the current element's name and namespace URI and combine them into an `XmlQualifiedName` that is then used for looking up the corresponding operation from the dictionary held by the operation selector.</span></span>  
  
```csharp
public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
{  
    XmlDictionaryReader bodyReader = message.GetReaderAtBodyContents();  
    XmlQualifiedName lookupQName = new  
       XmlQualifiedName(bodyReader.LocalName, bodyReader.NamespaceURI);  
    message = CreateMessageCopy(message,bodyReader);  
    if (dispatchDictionary.ContainsKey(lookupQName))  
    {  
         return dispatchDictionary[lookupQName];  
    }  
    else  
    {  
        return defaultOperationName;  
    }  
}  
```  
  
 <span data-ttu-id="2cd80-115">Tener acceso al cuerpo del mensaje con <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> o cualquiera de los otros métodos que proporcionan el acceso al contenido del cuerpo del mensaje produce que el mensaje marque como "lectura", que significa que el mensaje no es válido para cualquier otro procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2cd80-115">Accessing the message body with <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> or any of the other methods that provide access to the message's body content causes the message to be marked as "read", which means that the message is invalid for any further processing.</span></span> <span data-ttu-id="2cd80-116">Por consiguiente, el selector de la operación crea una copia del mensaje entrante con el método mostrado en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2cd80-116">Therefore, the operation selector creates a copy of the incoming message with the method shown in the following code.</span></span> <span data-ttu-id="2cd80-117">Dado que la posición del lector no se ha cambiado durante la inspección, el mensaje recientemente creado en el que se copian las propiedades de mensaje y los encabezados del mensaje también, lo que resulta en un en un clon exacto del mensaje original:</span><span class="sxs-lookup"><span data-stu-id="2cd80-117">Because the reader's position has not been changed during the inspection, it can be referenced by the newly created message to which the message properties and the message headers are also copied, which results in an exact clone of the original message:</span></span>  
  
```csharp
private Message CreateMessageCopy(Message message,
                                     XmlDictionaryReader body)  
{  
    Message copy = Message.CreateMessage(message.Version,message.Headers.Action,body);  
    copy.Headers.CopyHeaderFrom(message,0);  
    copy.Properties.CopyProperties(message.Properties);  
    return copy;  
}  
```  
  
## <a name="adding-an-operation-selector-to-a-service"></a><span data-ttu-id="2cd80-118">Agregar un selector de operación a un servicio</span><span class="sxs-lookup"><span data-stu-id="2cd80-118">Adding an Operation Selector to a Service</span></span>  
 <span data-ttu-id="2cd80-119">Los selectores de la operación de envío de servicio son extensiones del distribuidor de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2cd80-119">Service dispatch operation selectors are extensions to the Windows Communication Foundation (WCF) dispatcher.</span></span> <span data-ttu-id="2cd80-120">Para seleccionar los métodos en el canal de devolución de llamada de contratos dúplex, hay también selectores de operación de cliente que trabajan de manera muy similar a los selectores de operación de expedición aquí, pero que no se cubren explícitamente en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2cd80-120">For selecting methods on the callback channel of duplex contracts, there are also client operation selectors, which work very much like the dispatch operation selectors described here, but which are not explicitly covered in this sample.</span></span>  
  
 <span data-ttu-id="2cd80-121">Como la mayoría de las extensiones ejemplares de los servicios, los selectores de la operación de expedición se agregan al distribuidor utilizando los comportamientos.</span><span class="sxs-lookup"><span data-stu-id="2cd80-121">Like most service model extensions, dispatch operation selectors are added to the dispatcher using behaviors.</span></span> <span data-ttu-id="2cd80-122">Un *comportamiento* es un objeto de configuración que agrega una o más extensiones al tiempo de ejecución de envío (o al tiempo de ejecución del cliente) o cambia su configuración.</span><span class="sxs-lookup"><span data-stu-id="2cd80-122">A *behavior* is a configuration object, which either adds one or more extensions to the dispatch runtime (or to the client runtime) or otherwise changes its settings.</span></span>  
  
 <span data-ttu-id="2cd80-123">Dado que los selectores de la operación tienen el ámbito del contrato, el comportamiento adecuado para implementar aquí es <xref:System.ServiceModel.Description.IContractBehavior>.</span><span class="sxs-lookup"><span data-stu-id="2cd80-123">Because operation selectors have contract scope, the appropriate behavior to implement here is the <xref:System.ServiceModel.Description.IContractBehavior>.</span></span> <span data-ttu-id="2cd80-124">Dado que la interfaz se implementa como se muestra en una clase derivada <xref:System.Attribute> en el código siguiente, el comportamiento se puede agregar mediante declaración a cualquier contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="2cd80-124">Because the interface is implemented on a <xref:System.Attribute> derived class as shown in the following code, the behavior can be declaratively added to any service contract.</span></span> <span data-ttu-id="2cd80-125">Cuando se abre un<xref:System.ServiceModel.ServiceHost> y el tiempo de ejecución de la expedición está generado, todos los comportamientos buscados, bien como atributos en los contratos, operaciones o implementaciones del servicio, o bien como elemento en la configuración del servicio se agregan automáticamente y como consecuencia solicitan contribuir con las extensiones o modificar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2cd80-125">Whenever a <xref:System.ServiceModel.ServiceHost> is opened and the dispatch runtime is built, all behaviors found either as attributes on contracts, operations, and service implementations or as element in the service configuration are automatically added and subsequently asked to contribute extensions or modify the default configuration.</span></span>  
  
 <span data-ttu-id="2cd80-126">Para ser breve, el fragmento de código siguiente muestra solo la implementación del método <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, que realiza los cambios de configuración para el distribuidor en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2cd80-126">For brevity, the following code excerpt only shows the implementation of the method <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, which effects the configuration changes for the dispatcher in this sample.</span></span> <span data-ttu-id="2cd80-127">No se muestran los otros métodos porque vuelven al llamador sin hacer ningún trabajo.</span><span class="sxs-lookup"><span data-stu-id="2cd80-127">The other methods are not shown because they return to the caller without doing any work.</span></span>  
  
```csharp
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 <span data-ttu-id="2cd80-128">Primero, la implementación <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> prepara el diccionario de búsqueda para el selector de la operación procesa una iteración sobre los elementos <xref:System.ServiceModel.Description.OperationDescription> en <xref:System.ServiceModel.Description.ContractDescription>del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="2cd80-128">First, the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> implementation sets up the lookup dictionary for the operation selector by iterating over the <xref:System.ServiceModel.Description.OperationDescription> elements in the service endpoint's <xref:System.ServiceModel.Description.ContractDescription>.</span></span> <span data-ttu-id="2cd80-129">A continuación, cada descripción de la operación se inspecciona para la presencia del comportamiento `DispatchBodyElementAttribute`, una implementación de <xref:System.ServiceModel.Description.IOperationBehavior> que también se define en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2cd80-129">Then, each operation description is inspected for the presence of the `DispatchBodyElementAttribute` behavior, an implementation of <xref:System.ServiceModel.Description.IOperationBehavior> that is also defined in this sample.</span></span> <span data-ttu-id="2cd80-130">Aunque esta clase también es un comportamiento, es pasivo y no contribuye activamente con ningún cambio de configuración a la expedición en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2cd80-130">While this class is also a behavior, it is passive and does not actively contribute any configuration changes to the dispatch runtime.</span></span> <span data-ttu-id="2cd80-131">Todos sus métodos vuelven al llamador sin tomar ninguna medida.</span><span class="sxs-lookup"><span data-stu-id="2cd80-131">All of its methods return to the caller without taking any actions.</span></span> <span data-ttu-id="2cd80-132">El comportamiento de la operación solo existe para que los metadatos exigidos para el nuevo mecanismo de la expedición, a saber, el nombre completo del cuerpo del elemento en cuya aparición se selecciona una operación, puedan estar asociados a las operaciones respectivas.</span><span class="sxs-lookup"><span data-stu-id="2cd80-132">The operation behavior only exists so that the metadata required for the new dispatch mechanism, namely the qualified name of the body element on whose occurrence an operation is selected, can be associated with the respective operations.</span></span>  
  
 <span data-ttu-id="2cd80-133">Si se busca este tipo de comportamiento, un par de valor creado a partir del nombre completo de XML (propiedad`QName` ) y el nombre de la operación (propiedad`Name` ) se agrega al diccionario.</span><span class="sxs-lookup"><span data-stu-id="2cd80-133">If such a behavior is found, a value pair created from the XML qualified name (`QName` property) and the operation name (`Name` property) is added to the dictionary.</span></span>  
  
 <span data-ttu-id="2cd80-134">Una vez rellenado el diccionario, un nuevo `DispatchByBodyElementOperationSelector` se construye con esta información y se establece como el selector de la operación de la expedición en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="2cd80-134">Once the dictionary is populated, a new `DispatchByBodyElementOperationSelector` is constructed with this information and set as the operation selector of the dispatch runtime:</span></span>  
  
```csharp
public void ApplyDispatchBehavior(ContractDescription contractDescription, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatchRuntime)  
{  
    Dictionary<XmlQualifiedName,string> dispatchDictionary =
                     new Dictionary<XmlQualifiedName,string>();  
    foreach( OperationDescription operationDescription in
                              contractDescription.Operations )  
    {  
        DispatchBodyElementAttribute dispatchBodyElement =
   operationDescription.Behaviors.Find<DispatchBodyElementAttribute>();  
        if ( dispatchBodyElement != null )  
        {  
             dispatchDictionary.Add(dispatchBodyElement.QName,
                              operationDescription.Name);  
        }  
    }  
    dispatchRuntime.OperationSelector =
            new DispatchByBodyElementOperationSelector(  
               dispatchDictionary,
               dispatchRuntime.UnhandledDispatchOperation.Name);  
    }  
}  
```  
  
## <a name="implementing-the-service"></a><span data-ttu-id="2cd80-135">Implementar el servicio</span><span class="sxs-lookup"><span data-stu-id="2cd80-135">Implementing the Service</span></span>  
 <span data-ttu-id="2cd80-136">El comportamiento implementado directamente en este ejemplo afecta a cómo se interpretan los mensajes de la conexión y los envían, lo cual es una función del contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="2cd80-136">The behavior implemented in this sample directly affects how messages from the wire are interpreted and dispatched, which is a function of the service contract.</span></span> <span data-ttu-id="2cd80-137">Por consiguiente, el comportamiento se debería declarar en el nivel del contrato de servicios en cualquier implementación del servicio que decida utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="2cd80-137">Consequently, the behavior should be declared on the service contract level in any service implementation that chooses to use it.</span></span>  
  
 <span data-ttu-id="2cd80-138">El servicio de proyecto de ejemplo aplica el `DispatchByBodyElementBehaviorAttribute` comportamiento del contrato al `IDispatchedByBody` contrato de servicio y etiqueta cada una de las dos operaciones `OperationForBodyA()` y `OperationForBodyB()` con un comportamiento de la `DispatchBodyElementAttribute` operación.</span><span class="sxs-lookup"><span data-stu-id="2cd80-138">The sample project service applies the `DispatchByBodyElementBehaviorAttribute` contract behavior to the `IDispatchedByBody` service contract and labels each of the two operations `OperationForBodyA()` and `OperationForBodyB()` with a `DispatchBodyElementAttribute` operation behavior.</span></span> <span data-ttu-id="2cd80-139">Cuando se abre un host del servicio para un servicio que implementa este contrato, este metadato lo escoge previamente el generador del distribuidor, tal y como se ha descrito previamente.</span><span class="sxs-lookup"><span data-stu-id="2cd80-139">When a service host for a service that implements this contract is opened, this metadata is picked up by the dispatcher builder as previously described.</span></span>  
  
 <span data-ttu-id="2cd80-140">Dado que el selector de la operación se envía solamente basado en el elemento de cuerpo del mensaje y omite la "Acción", para indicar el tiempo de ejecución se exige no comprobar el encabezado "Acción" en las respuestas devueltas asignando el carácter comodín "\*" a la propiedad `ReplyAction` de <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2cd80-140">Because the operation selector dispatches solely based on the message body element and ignores the "Action", it is required to tell the runtime not to check the "Action" header on the returned replies by assigning the wildcard "\*" to the `ReplyAction` property of <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="2cd80-141">Además, es necesario tener una operación predeterminada que tenga la propiedad "Action" establecida en el carácter comodín " \* ".</span><span class="sxs-lookup"><span data-stu-id="2cd80-141">Furthermore, it is required to have a default operation that has the "Action" property set to the wildcard "\*".</span></span> <span data-ttu-id="2cd80-142">La operación predeterminada recibe todos los mensajes que no se pueden enviar y no tienen `DispatchBodyElementAttribute`:</span><span class="sxs-lookup"><span data-stu-id="2cd80-142">The default operation receives all messages which cannot be dispatched and does not have a `DispatchBodyElementAttribute`:</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
                            DispatchByBodyElementBehavior]  
public interface IDispatchedByBody  
{  
    [OperationContract(ReplyAction="*"),
     DispatchBodyElement("bodyA","http://tempuri.org")]  
    Message OperationForBodyA(Message msg);  
    [OperationContract(ReplyAction = "*"),
     DispatchBodyElement("bodyB", "http://tempuri.org")]  
    Message OperationForBodyB(Message msg);  
    [OperationContract(Action="*", ReplyAction="*")]  
    Message DefaultOperation(Message msg);  
}  
```  
  
 <span data-ttu-id="2cd80-143">La implementación de servicio de ejemplo es sencilla.</span><span class="sxs-lookup"><span data-stu-id="2cd80-143">The sample service implementation is straightforward.</span></span> <span data-ttu-id="2cd80-144">Cada método ajusta el mensaje recibido en un mensaje de respuesta y lo devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="2cd80-144">Every method wraps the received message into a reply message and echoes it back to the client.</span></span>  
  
## <a name="running-and-building-the-sample"></a><span data-ttu-id="2cd80-145">Ejecutar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd80-145">Running and Building the Sample</span></span>  
 <span data-ttu-id="2cd80-146">Al ejecutar el ejemplo, el contenido del cuerpo de las respuestas de la operación se muestra en la ventana de la consola del cliente de una manera parecida al resultado siguiente (formateado).</span><span class="sxs-lookup"><span data-stu-id="2cd80-146">When you run the sample, the body content of the operation responses are displayed in the client console window similar to the following (formatted) output.</span></span>  
  
 <span data-ttu-id="2cd80-147">El cliente envía tres mensajes al servicio cuyo elemento de contenido de cuerpo se denomina `bodyA`, `bodyB`y `bodyX`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2cd80-147">The client sends three messages to the service whose body content element is named `bodyA`, `bodyB`, and `bodyX`, respectively.</span></span> <span data-ttu-id="2cd80-148">Como se puede diferir de la descripción anterior y el contrato de servicios mostrado, el mensaje entrante con el elemento `bodyA` se envía al método `OperationForBodyA()`.</span><span class="sxs-lookup"><span data-stu-id="2cd80-148">As can be deferred from the previous description and the service contract shown, the incoming message with the `bodyA` element is dispatched to the `OperationForBodyA()` method.</span></span> <span data-ttu-id="2cd80-149">Dado que no hay ningún destino de la expedición explícito para el mensaje con el cuerpo del elemento `bodyX`, el mensaje se envía a `DefaultOperation()`.</span><span class="sxs-lookup"><span data-stu-id="2cd80-149">Because there is no explicit dispatch target for the message with the `bodyX` body element, the message is dispatched to the `DefaultOperation()`.</span></span> <span data-ttu-id="2cd80-150">Cada una de las operaciones de servicio contiene el cuerpo del mensaje recibido en un elemento concreto al método y vuelve a él, lo cual se hace para poner en correlación claramente los mensajes de entrada y salida para obtener este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cd80-150">Each of the service operations wraps the received message body into an element specific to the method and returns it, which is done to correlate input and output messages clearly for this sample:</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyA xmlns="http://tempuri.org">  
   <q:bodyA xmlns:q="http://tempuri.org">test</q:bodyA>  
</replyBodyA>  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyB xmlns="http://tempuri.org">  
  <q:bodyB xmlns:q="http://tempuri.org">test</q:bodyB>  
</replyBodyB>  
<?xml version="1.0" encoding="IBM437"?>  
<replyDefault xmlns="http://tempuri.org">  
   <q:bodyX xmlns:q="http://tempuri.org">test</q:bodyX>  
</replyDefault>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2cd80-151">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd80-151">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2cd80-152">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2cd80-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="2cd80-153">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2cd80-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="2cd80-154">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2cd80-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2cd80-155">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2cd80-155">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2cd80-156">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2cd80-156">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2cd80-157">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2cd80-157">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2cd80-158">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2cd80-158">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
