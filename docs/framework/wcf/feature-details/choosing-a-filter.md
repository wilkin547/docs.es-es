---
title: Elegir un filtro
ms.date: 03/30/2017
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
ms.openlocfilehash: 282f6e9e2bc986feee0d1825ee9d87217d453e50
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964815"
---
# <a name="choosing-a-filter"></a><span data-ttu-id="63255-102">Elegir un filtro</span><span class="sxs-lookup"><span data-stu-id="63255-102">Choosing a Filter</span></span>
<span data-ttu-id="63255-103">Al configurar el servicio de enrutamiento, es importante seleccionar filtros de mensajes adecuados y configurarlos para poder obtener coincidencias exactas con los mensajes que recibe.</span><span class="sxs-lookup"><span data-stu-id="63255-103">When configuring the Routing Service, it is important to select correct message filters and configure them to allow you to make exact matches against the messages you receive.</span></span> <span data-ttu-id="63255-104">Si los filtros que selecciona son demasiado anchos en sus coincidencias o se configuran incorrectamente, los mensajes se enrutan de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="63255-104">If the filters you select are overly broad in their matches or are incorrectly configured, messages are routed incorrectly.</span></span> <span data-ttu-id="63255-105">Si los filtros son demasiado restrictivos, puede que no tenga ninguna ruta válida disponible para algunos de sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="63255-105">If the filters are too restrictive, you may not have any valid routes available for some of your messages.</span></span>

## <a name="filter-types"></a><span data-ttu-id="63255-106">Tipos de filtro</span><span class="sxs-lookup"><span data-stu-id="63255-106">Filter Types</span></span>

<span data-ttu-id="63255-107">Al seleccionar los filtros que utiliza el servicio de enrutamiento, es importante que entienda cómo funciona cada filtro, así como qué información está disponible como parte de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="63255-107">When selecting the filters that are used by the Routing Service, it is important that you understand how each filter works as well as what information is available as part of the incoming messages.</span></span> <span data-ttu-id="63255-108">Por ejemplo, si todos los mensajes se reciben en el mismo punto de conexión, los filtros EndpointName y de dirección no son útiles porque todos los mensajes coinciden con dichos filtros.</span><span class="sxs-lookup"><span data-stu-id="63255-108">For instance, if all messages are received over the same endpoint, the Address and EndpointName filters are not useful because all messages match these filters.</span></span>

### <a name="action"></a><span data-ttu-id="63255-109">Acción de</span><span class="sxs-lookup"><span data-stu-id="63255-109">Action</span></span>

<span data-ttu-id="63255-110">El filtro de acción inspecciona la propiedad <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A>.</span><span class="sxs-lookup"><span data-stu-id="63255-110">The Action filter inspects the <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> property.</span></span> <span data-ttu-id="63255-111">Si el contenido del encabezado de acción en el mensaje coincide con el valor de datos de filtro especificado en la configuración del filtro, este filtro devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="63255-111">If the contents of the Action header in the message match the filter data value specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="63255-112">En el ejemplo siguiente se define un `FilterElement` que usa el filtro de acción para hacer coincidir los mensajes con un encabezado de acción que contiene un valor de `http://namespace/contract/operation/`.</span><span class="sxs-lookup"><span data-stu-id="63255-112">The following example defines a `FilterElement` that uses the Action filter to match messages with an action header that contains a value of `http://namespace/contract/operation/`.</span></span>

```xml
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />
```

```csharp
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
```

<span data-ttu-id="63255-113">Se debería utilizar este filtro al enrutar mensajes que contienen un encabezado de acción único.</span><span class="sxs-lookup"><span data-stu-id="63255-113">This filter should be used when routing messages that contain a unique Action header.</span></span>

### <a name="endpointaddress"></a><span data-ttu-id="63255-114">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="63255-114">EndpointAddress</span></span>

<span data-ttu-id="63255-115">El filtro EndpointAddress inspecciona las direcciones EndpointAddress en las que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="63255-115">The EndpointAddress filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="63255-116">Si la dirección a la que llega el mensaje coincide exactamente con la dirección del filtro especificada en la configuración del filtro, este filtro devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="63255-116">If the address that the message arrives at exactly matches the filter address specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="63255-117">En el ejemplo siguiente se define un `FilterElement` que usa el filtro de direcciones para buscar coincidencias con cualquier mensaje dirigido a "http://\<hostname >/vdir/s.SVC/b".</span><span class="sxs-lookup"><span data-stu-id="63255-117">The following example defines a `FilterElement` that uses the Address filter to match any messages addressed to "http://\<hostname>/vdir/s.svc/b".</span></span>

```xml
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> <span data-ttu-id="63255-118">Es importante tener en cuenta que la parte del nombre de host de una dirección puede diferir dependiendo de si el cliente utiliza el nombre de dominio completo, el nombre NetBIOS, la dirección IP u otro nombre.</span><span class="sxs-lookup"><span data-stu-id="63255-118">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="63255-119">Dado que los valores distintos pueden hacer referencia al mismo host, el comportamiento predeterminado para esta comparación es no utilizar la parte del nombre de host de la dirección al realizar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="63255-119">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>
>
> <span data-ttu-id="63255-120">Este comportamiento se puede modificar para permitir que la comparación evalúe el nombre de host al configurar el servicio de enrutamiento mediante programación.</span><span class="sxs-lookup"><span data-stu-id="63255-120">This behavior can be modified to allow the comparison to evaluate the host name when configuring the Routing Service programmatically.</span></span>

<span data-ttu-id="63255-121">Se debería utilizar este filtro cuando los mensajes entrantes se dirijan a una dirección única.</span><span class="sxs-lookup"><span data-stu-id="63255-121">This filter should be used when the incoming messages are addressed to a unique address.</span></span>

### <a name="endpointaddressprefix"></a><span data-ttu-id="63255-122">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="63255-122">EndpointAddressPrefix</span></span>

<span data-ttu-id="63255-123">El filtro EndpointAddressPrefix es similar al filtro EndpointAddress.</span><span class="sxs-lookup"><span data-stu-id="63255-123">The EndpointAddressPrefix filter is similar to the EndpointAddress filter.</span></span> <span data-ttu-id="63255-124">El filtro EndpointAddressPrefix inspecciona las direcciones EndpointAddress en las que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="63255-124">The EndpointAddressPrefix filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="63255-125">No obstante, el filtro EndpointAddressPrefix actúa como comodín, coincidiendo con las direcciones que comienzan con el valor especificado en la configuración del filtro.</span><span class="sxs-lookup"><span data-stu-id="63255-125">However the EndpointAddressPrefix filter acts as a wildcard by matching addresses that begin with the value specified in the filter configuration.</span></span> <span data-ttu-id="63255-126">En el ejemplo siguiente se define un `FilterElement` que usa el filtro EndpointAddressPrefix para buscar coincidencias con cualquier mensaje dirigido a `http://<hostname>/vdir*`.</span><span class="sxs-lookup"><span data-stu-id="63255-126">The following example defines a `FilterElement` that uses the EndpointAddressPrefix filter to match any messages addressed to `http://<hostname>/vdir*`.</span></span>

```xml
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />
```

```csharp
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> <span data-ttu-id="63255-127">Es importante tener en cuenta que la parte del nombre de host de una dirección puede diferir dependiendo de si el cliente utiliza el nombre de dominio completo, el nombre NetBIOS, la dirección IP u otro nombre.</span><span class="sxs-lookup"><span data-stu-id="63255-127">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="63255-128">Dado que los valores distintos pueden hacer referencia al mismo host, el comportamiento predeterminado para esta comparación es no utilizar la parte del nombre de host de la dirección al realizar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="63255-128">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>

<span data-ttu-id="63255-129">Se debería utilizar este filtro al enrutar mensajes entrantes que comparten un prefijo de dirección común.</span><span class="sxs-lookup"><span data-stu-id="63255-129">This filter should be used when routing incoming messages that share a common address prefix.</span></span>

### <a name="and"></a><span data-ttu-id="63255-130">AND</span><span class="sxs-lookup"><span data-stu-id="63255-130">AND</span></span>

<span data-ttu-id="63255-131">El filtro AND no filtra directamente un valor dentro del mensaje, sino que le permite combinar dos filtros para crear una condición `AND` donde ambos filtros deben coincidir con el mensaje para que el filtro AND lo evalúe como `true`.</span><span class="sxs-lookup"><span data-stu-id="63255-131">The AND filter does not directly filter on a value within a message, but allows you to combine two other filters to create an `AND` condition where both filters must match the message before the AND filter evaluates to `true`.</span></span> <span data-ttu-id="63255-132">Esto le permite crear filtros complejos que solo coinciden si todos los sub-filtros coinciden.</span><span class="sxs-lookup"><span data-stu-id="63255-132">This allows you to create complex filters that only match if all the sub-filters match.</span></span> <span data-ttu-id="63255-133">El siguiente ejemplo define un filtro de dirección y un filtro de acción y, a continuación, define un filtro AND que evalúa un mensaje con respecto a los filtros de acción y dirección.</span><span class="sxs-lookup"><span data-stu-id="63255-133">The following example defines an address filter and an action filter, and then defines an AND filter that evaluates a message against both the address and action filters.</span></span> <span data-ttu-id="63255-134">Si tanto el filtro de dirección como el de acción coinciden, entonces el filtro AND devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="63255-134">If both the address and the action filters match, then the AND filter returns `true`.</span></span>

```xml
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);
```

<span data-ttu-id="63255-135">Se debería utilizar este filtro al tener que combinar la lógica de varios filtros para determinar cuándo se debería realizar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="63255-135">This filter should be used when you must combine the logic from multiple filters to determine when a match should be made.</span></span> <span data-ttu-id="63255-136">Por ejemplo, si tiene varios destinos que solo deben recibir ciertas combinaciones de acciones y mensajes en determinadas direcciones, puede utilizar un filtro AND para combinar los filtros de acción y dirección necesarios.</span><span class="sxs-lookup"><span data-stu-id="63255-136">For example, if you have multiple destinations that must receive only certain combinations of actions and messages to particular addresses, you can use an AND filter to combine the necessary Action and Address filters.</span></span>

### <a name="custom"></a><span data-ttu-id="63255-137">Personalizado</span><span class="sxs-lookup"><span data-stu-id="63255-137">Custom</span></span>

<span data-ttu-id="63255-138">Al seleccionar el tipo de filtro personalizado, debe proporcionar un valor de customType que contenga el tipo del ensamblado que contiene la implementación de **MessageFilter** que se va a usar para este filtro.</span><span class="sxs-lookup"><span data-stu-id="63255-138">When selecting the Custom filter type, you must provide a customType value that contains the type of the assembly that contains the **MessageFilter** implementation to be used for this filter.</span></span> <span data-ttu-id="63255-139">Además, filterData debe contener cualquier valor que el filtro personalizado pueda requerir en su evaluación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="63255-139">Additionally, filterData must contain any values that the custom filter may require in its evaluation of messages.</span></span> <span data-ttu-id="63255-140">En el siguiente ejemplo, se define un `FilterElement` que utiliza la implementación `CustomAssembly.MyCustomMsgFilter` MessageFilter.</span><span class="sxs-lookup"><span data-stu-id="63255-140">The following example defines a `FilterElement` that uses the `CustomAssembly.MyCustomMsgFilter` MessageFilter implementation.</span></span>

```xml
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />
```

```csharp
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");
```

<span data-ttu-id="63255-141">Si necesita realizar una lógica de coincidencia personalizada con un mensaje que no esté incluido en los filtros proporcionados con [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], debe crear un filtro personalizado que sea una implementación de la clase **MessageFilter** .</span><span class="sxs-lookup"><span data-stu-id="63255-141">If you need to perform custom matching logic against a message that is not covered by the filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], you must create a custom filter that is an implementation of the **MessageFilter** class.</span></span> <span data-ttu-id="63255-142">Por ejemplo, puede crear un filtro personalizado que compare un campo en el mensaje entrante con una lista de valores conocidos indicados al filtro como configuración, o que aplica un algoritmo hash a un elemento de mensaje determinado y, a continuación, examina ese valor para determinar si el filtro debería devolver `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="63255-142">For example, you might create a custom filter that compares a field in the incoming message against a list of known values given to the filter as configuration, or that hashes a particular message element and then examines that value to determine whether the filter should return `true` or `false`.</span></span>

### <a name="endpointname"></a><span data-ttu-id="63255-143">EndpointName</span><span class="sxs-lookup"><span data-stu-id="63255-143">EndpointName</span></span>

<span data-ttu-id="63255-144">El filtro EndpointName inspecciona el nombre del punto de conexión que recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="63255-144">The EndpointName filter inspects the name of the endpoint that received the message.</span></span> <span data-ttu-id="63255-145">En el ejemplo siguiente se define un `FilterElement` que usa el filtro EndpointName para enrutar los mensajes recibidos en "SvcEndpoint".</span><span class="sxs-lookup"><span data-stu-id="63255-145">The following example defines a `FilterElement` that uses the EndpointName filter to route messages received on the "SvcEndpoint".</span></span>

```xml
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />
```

```csharp
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");
```

<span data-ttu-id="63255-146">Este filtro es útil cuando el servicio de enrutamiento expone más de un punto de conexión de servicio con nombre.</span><span class="sxs-lookup"><span data-stu-id="63255-146">This filter is useful when the Routing Service exposes more than one named service endpoint.</span></span> <span data-ttu-id="63255-147">Por ejemplo, puede exponer dos puntos de conexión que utiliza el servicio de enrutamiento para recibir mensajes; uno lo emplean clientes prioritarios que requieren un procesamiento en tiempo real de sus mensajes, mientras que el otro punto de conexión recibe mensajes que no están sujetos a una limitación temporal.</span><span class="sxs-lookup"><span data-stu-id="63255-147">For example, you might expose two endpoints that the Routing Service uses to receive messages; one is used by priority customers who require real-time processing of their messages, while the other endpoint receives messages that are not time sensitive.</span></span>

<span data-ttu-id="63255-148">Aunque a menudo pueda usar una dirección completa coincidente para determinar en qué punto de conexión se ha recibido un mensaje, el uso del nombre de punto de conexión definido es un método abreviado recomendable que suele originar menos errores, sobre todo al configurar un servicio de enrutamiento mediante un archivo de configuración (donde los nombres de puntos de conexión son un atributo necesario).</span><span class="sxs-lookup"><span data-stu-id="63255-148">While you can often use full address matching to determine which endpoint a message was received on, using the defined endpoint name instead is a convenient shortcut that is often less error prone, especially when configuring a Routing Service using a configuration file (where endpoint names are a required attribute).</span></span>

### <a name="matchall"></a><span data-ttu-id="63255-149">MatchAll</span><span class="sxs-lookup"><span data-stu-id="63255-149">MatchAll</span></span>

<span data-ttu-id="63255-150">El filtro MatchAll coincide con cualquier mensaje recibido.</span><span class="sxs-lookup"><span data-stu-id="63255-150">The MatchAll filter matches any received message.</span></span> <span data-ttu-id="63255-151">Es útil si siempre debe enrutar todos los mensajes recibidos a un extremo concreto, como un servicio del registro que almacena una copia de todos los mensajes recibidos.</span><span class="sxs-lookup"><span data-stu-id="63255-151">It is useful if you must always route all received messages to a specific endpoint, such as a logging service that stores a copy of all received messages.</span></span> <span data-ttu-id="63255-152">En el siguiente ejemplo, se define un `FilterElement` que utiliza el filtro MatchAll.</span><span class="sxs-lookup"><span data-stu-id="63255-152">The following example defines a `FilterElement` that uses the MatchAll filter.</span></span>

```xml
<filter name="matchAll1" filterType="MatchAll" />
```

```csharp
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();
```

### <a name="xpath"></a><span data-ttu-id="63255-153">XPath</span><span class="sxs-lookup"><span data-stu-id="63255-153">XPath</span></span>

<span data-ttu-id="63255-154">El filtro XPath le permite especificar una consulta XPath que se usa para inspeccionar un elemento concreto dentro del mensaje.</span><span class="sxs-lookup"><span data-stu-id="63255-154">The XPath filter allows you to specify an XPath query that is used to inspect a specific element within the message.</span></span> <span data-ttu-id="63255-155">El filtrado XPath es una opción de filtrado eficaz que le permite inspeccionar directamente cualquier entrada direccionable XML dentro del mensaje; sin embargo, requiere que posea conocimientos específicos sobre la estructura de los mensajes que recibe.</span><span class="sxs-lookup"><span data-stu-id="63255-155">XPath filtering is a powerful filtering option that allows you to directly inspect any XML addressable entry within the message; however it requires that you have specific knowledge of the structure of the messages that you are receiving.</span></span> <span data-ttu-id="63255-156">En el ejemplo siguiente se define un `FilterElement` que usa el filtro XPath para inspeccionar el mensaje para un elemento denominado "Element" en el espacio de nombres al que hace referencia el prefijo de espacio de nombres "NS".</span><span class="sxs-lookup"><span data-stu-id="63255-156">The following example defines a `FilterElement` that uses the XPath filter to inspect the message for an element named "element" within the namespace referenced by the "ns" namespace prefix.</span></span>

```xml
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />
```

```csharp
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");
```

<span data-ttu-id="63255-157">Este filtro es útil si sabe que los mensajes que recibe contienen un valor concreto.</span><span class="sxs-lookup"><span data-stu-id="63255-157">This filter is useful if you know that the messages you are receiving contain a specific value.</span></span> <span data-ttu-id="63255-158">Por ejemplo, si hospeda dos versiones del mismo servicio y sabe que los mensajes enviados a la versión más reciente del servicio contienen un valor único en un encabezado personalizado, puede crear un filtro que utilice XPath para desplazarse hasta este encabezado y comparar el valor del encabezado con otro indicado en la configuración del filtro para determinar si el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="63255-158">For example, if you are hosting two versions of the same service and you know that messages addressed to the newer version of the service contain a unique value in a custom header, you can create a filter that uses XPath to navigate to this header and compares the value present in the header to another given in the filter configuration to determine if the filter matches.</span></span>

<span data-ttu-id="63255-159">Dado que las consultas XPath suelen incluir espacios de nombres únicos, que son a menudo valores de cadena largos y complejos, el filtro XPath le permite usar la tabla de espacio de nombres para definir prefijos únicos para los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="63255-159">Because XPath queries often contain unique namespaces, which are often lengthy or complex string values, the XPath filter allows you to use the namespace table to define unique prefixes for your namespaces.</span></span> <span data-ttu-id="63255-160">Para obtener más información acerca de la tabla de espacio de nombres, vea [filtros de mensajes](../../../../docs/framework/wcf/feature-details/message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="63255-160">For more information about the namespace table, see [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>

<span data-ttu-id="63255-161">Para obtener más información sobre el diseño de consultas XPath, vea [Sintaxis de XPath](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="63255-161">For more information about designing XPath queries, see [XPath Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="63255-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="63255-162">See also</span></span>

- [<span data-ttu-id="63255-163">Filtros de mensajes</span><span class="sxs-lookup"><span data-stu-id="63255-163">Message Filters</span></span>](../../../../docs/framework/wcf/feature-details/message-filters.md)
- [<span data-ttu-id="63255-164">Uso de los filtros</span><span class="sxs-lookup"><span data-stu-id="63255-164">How To: Use Filters</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-filters.md)
