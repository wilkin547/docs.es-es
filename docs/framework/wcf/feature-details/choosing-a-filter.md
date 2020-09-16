---
title: Elegir un filtro
ms.date: 03/30/2017
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
ms.openlocfilehash: 2f96e7001a41682ef595d003e87daa06d0244f3b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559394"
---
# <a name="choosing-a-filter"></a>Elegir un filtro
Al configurar el servicio de enrutamiento, es importante seleccionar filtros de mensajes adecuados y configurarlos para poder obtener coincidencias exactas con los mensajes que recibe. Si los filtros que selecciona son demasiado anchos en sus coincidencias o se configuran incorrectamente, los mensajes se enrutan de forma incorrecta. Si los filtros son demasiado restrictivos, puede que no tenga ninguna ruta válida disponible para algunos de sus mensajes.

## <a name="filter-types"></a>Tipos de filtros

Al seleccionar los filtros que utiliza el servicio de enrutamiento, es importante que entienda cómo funciona cada filtro, así como qué información está disponible como parte de los mensajes entrantes. Por ejemplo, si todos los mensajes se reciben en el mismo punto de conexión, los filtros EndpointName y de dirección no son útiles porque todos los mensajes coinciden con dichos filtros.

### <a name="action"></a>Acción

El filtro de acción inspecciona la propiedad <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A>. Si el contenido del encabezado de acción en el mensaje coincide con el valor de datos de filtro especificado en la configuración del filtro, este filtro devuelve `true`. En el ejemplo siguiente se define un `FilterElement` que utiliza el filtro de acción para hacer coincidir los mensajes con un encabezado de acción que contiene un valor de `http://namespace/contract/operation/` .

```xml
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />
```

```csharp
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
```

Se debería utilizar este filtro al enrutar mensajes que contienen un encabezado de acción único.

### <a name="endpointaddress"></a>EndpointAddress

El filtro EndpointAddress inspecciona las direcciones EndpointAddress en las que se recibió el mensaje. Si la dirección a la que llega el mensaje coincide exactamente con la dirección del filtro especificada en la configuración del filtro, este filtro devuelve `true`. En el ejemplo siguiente se define un `FilterElement` que utiliza el filtro de direcciones para buscar coincidencias con los mensajes dirigidos a "http:// \<hostname> /vdir/s.SVC/b".

```xml
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> Es importante tener en cuenta que la parte del nombre de host de una dirección puede diferir dependiendo de si el cliente utiliza el nombre de dominio completo, el nombre NetBIOS, la dirección IP u otro nombre. Dado que los valores distintos pueden hacer referencia al mismo host, el comportamiento predeterminado para esta comparación es no utilizar la parte del nombre de host de la dirección al realizar coincidencias.
>
> Este comportamiento se puede modificar para permitir que la comparación evalúe el nombre de host al configurar el servicio de enrutamiento mediante programación.

Se debería utilizar este filtro cuando los mensajes entrantes se dirijan a una dirección única.

### <a name="endpointaddressprefix"></a>EndpointAddressPrefix

El filtro EndpointAddressPrefix es similar al filtro EndpointAddress. El filtro EndpointAddressPrefix inspecciona las direcciones EndpointAddress en las que se recibió el mensaje. No obstante, el filtro EndpointAddressPrefix actúa como comodín, coincidiendo con las direcciones que comienzan con el valor especificado en la configuración del filtro. En el ejemplo siguiente se define un `FilterElement` que utiliza el filtro EndpointAddressPrefix para buscar coincidencias con los mensajes dirigidos a `http://<hostname>/vdir*` .

```xml
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />
```

```csharp
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> Es importante tener en cuenta que la parte del nombre de host de una dirección puede diferir dependiendo de si el cliente utiliza el nombre de dominio completo, el nombre NetBIOS, la dirección IP u otro nombre. Dado que los valores distintos pueden hacer referencia al mismo host, el comportamiento predeterminado para esta comparación es no utilizar la parte del nombre de host de la dirección al realizar coincidencias.

Se debería utilizar este filtro al enrutar mensajes entrantes que comparten un prefijo de dirección común.

### <a name="and"></a>y

El filtro AND no filtra directamente un valor dentro del mensaje, sino que le permite combinar dos filtros para crear una condición `AND` donde ambos filtros deben coincidir con el mensaje para que el filtro AND lo evalúe como `true`. Esto le permite crear filtros complejos que solo coinciden si todos los sub-filtros coinciden. El siguiente ejemplo define un filtro de dirección y un filtro de acción y, a continuación, define un filtro AND que evalúa un mensaje con respecto a los filtros de acción y dirección. Si tanto el filtro de dirección como el de acción coinciden, entonces el filtro AND devuelve `true`.

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

Se debería utilizar este filtro al tener que combinar la lógica de varios filtros para determinar cuándo se debería realizar una coincidencia. Por ejemplo, si tiene varios destinos que solo deben recibir ciertas combinaciones de acciones y mensajes en determinadas direcciones, puede utilizar un filtro AND para combinar los filtros de acción y dirección necesarios.

### <a name="custom"></a>Personalizado

Al seleccionar el tipo de filtro personalizado, debe proporcionar un valor de customType que contenga el tipo del ensamblado que contiene la implementación de **MessageFilter** que se va a usar para este filtro. Además, filterData debe contener cualquier valor que el filtro personalizado pueda requerir en su evaluación de mensajes. En el siguiente ejemplo, se define un `FilterElement` que utiliza la implementación `CustomAssembly.MyCustomMsgFilter` MessageFilter.

```xml
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />
```

```csharp
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");
```

Si necesita realizar una lógica de coincidencia personalizada con un mensaje que no esté incluido en los filtros proporcionados con [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] , debe crear un filtro personalizado que sea una implementación de la clase **MessageFilter** . Por ejemplo, puede crear un filtro personalizado que compare un campo en el mensaje entrante con una lista de valores conocidos indicados al filtro como configuración, o que aplica un algoritmo hash a un elemento de mensaje determinado y, a continuación, examina ese valor para determinar si el filtro debería devolver `true` o `false`.

### <a name="endpointname"></a>EndpointName

El filtro EndpointName inspecciona el nombre del punto de conexión que recibió el mensaje. En el ejemplo siguiente se define un `FilterElement` que utiliza el filtro EndpointName para enrutar los mensajes recibidos en "SvcEndpoint".

```xml
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />
```

```csharp
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");
```

Este filtro es útil cuando el servicio de enrutamiento expone más de un punto de conexión de servicio con nombre. Por ejemplo, puede exponer dos puntos de conexión que utiliza el servicio de enrutamiento para recibir mensajes; uno lo emplean clientes prioritarios que requieren un procesamiento en tiempo real de sus mensajes, mientras que el otro punto de conexión recibe mensajes que no están sujetos a una limitación temporal.

Aunque a menudo pueda usar una dirección completa coincidente para determinar en qué punto de conexión se ha recibido un mensaje, el uso del nombre de punto de conexión definido es un método abreviado recomendable que suele originar menos errores, sobre todo al configurar un servicio de enrutamiento mediante un archivo de configuración (donde los nombres de puntos de conexión son un atributo necesario).

### <a name="matchall"></a>MatchAll

El filtro MatchAll coincide con cualquier mensaje recibido. Es útil si siempre debe enrutar todos los mensajes recibidos a un extremo concreto, como un servicio del registro que almacena una copia de todos los mensajes recibidos. En el siguiente ejemplo, se define un `FilterElement` que utiliza el filtro MatchAll.

```xml
<filter name="matchAll1" filterType="MatchAll" />
```

```csharp
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();
```

### <a name="xpath"></a>XPath

El filtro XPath le permite especificar una consulta XPath que se usa para inspeccionar un elemento concreto dentro del mensaje. El filtrado XPath es una opción de filtrado eficaz que le permite inspeccionar directamente cualquier entrada direccionable XML dentro del mensaje; sin embargo, requiere que posea conocimientos específicos sobre la estructura de los mensajes que recibe. En el ejemplo siguiente se define un `FilterElement` que utiliza el filtro XPath para inspeccionar el mensaje para un elemento denominado "Element" en el espacio de nombres al que hace referencia el prefijo de espacio de nombres "NS".

```xml
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />
```

```csharp
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");
```

Este filtro es útil si sabe que los mensajes que recibe contienen un valor concreto. Por ejemplo, si hospeda dos versiones del mismo servicio y sabe que los mensajes enviados a la versión más reciente del servicio contienen un valor único en un encabezado personalizado, puede crear un filtro que utilice XPath para desplazarse hasta este encabezado y comparar el valor del encabezado con otro indicado en la configuración del filtro para determinar si el filtro coincide.

Dado que las consultas XPath suelen incluir espacios de nombres únicos, que son a menudo valores de cadena largos y complejos, el filtro XPath le permite usar la tabla de espacio de nombres para definir prefijos únicos para los espacios de nombres. Para obtener más información acerca de la tabla de espacio de nombres, vea [filtros de mensajes](message-filters.md).

Para obtener más información sobre el diseño de consultas XPath, vea [Sintaxis de XPath](/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).

## <a name="see-also"></a>Vea también

- [Filtros de mensajes](message-filters.md)
- [Cómo usar los filtros](how-to-use-filters.md)
