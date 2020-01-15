---
title: Filtrado
ms.date: 03/30/2017
ms.assetid: 4002946c-e34a-4356-8cfb-e25912a4be63
ms.openlocfilehash: efbedc16fe48d83cdc4223862bc691e9cbe15c10
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964290"
---
# <a name="filtering"></a>Filtrado
El sistema de filtrado de Windows Communication Foundation (WCF) puede usar filtros declarativos para hacer coincidir los mensajes y tomar decisiones operativas. Puede utilizar filtros para determinar qué hacer con un mensaje examinando parte del mensaje. Un proceso de cola, por ejemplo, puede utilizar una consulta de XPath 1.0 para comprobar el elemento de prioridad de un encabezado conocido para determinar si poner un mensaje al principio de la cola.  
  
 El sistema de filtrado se compone de un conjunto de clases que pueden determinar eficazmente cuál de un conjunto de filtros se `true` para un determinado mensaje de WCF.  
  
 El sistema de filtrado es un componente básico de la mensajería de WCF; está diseñada para ser muy rápida. Cada implementación de filtro se ha optimizado para un tipo determinado de coincidencia con los mensajes de WCF.  
  
 El sistema de filtrado no es seguro para subprocesos. La aplicación debe administrar las semánticas de bloqueo. No obstante, sí que admite un sistema de escritura único y multilector.  
  
## <a name="where-filtering-fits"></a>Dónde encaja el filtrado  
 El filtrado se realiza una vez que se recibe un mensaje y es parte del proceso de enviar el mensaje al componente de aplicación apropiado. El diseño del sistema de filtrado aborda los requisitos de varios subsistemas WCF, incluidos la mensajería, el enrutamiento, la seguridad, el control de eventos y la administración del sistema.  
  
## <a name="filters"></a>Filtros.  
 El motor del filtro tiene dos componentes primarios, filtros y tablas de filtro. Un filtro toma decisiones booleanas sobre un mensaje en función de condiciones lógicas especificadas por el usuario. Los filtros implementan la clase <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 Los métodos de <xref:System.ServiceModel.Dispatcher.MessageFilter.Match%2A> se utilizan para determinar si un mensaje satisface un filtro. Uno de los métodos prueba el encabezado del mensaje, pero no puede inspeccionar el cuerpo del mensaje. El otro método toma un *búfer de mensajes* como parámetro de entrada y puede inspeccionar el cuerpo del mensaje.  
  
 Normalmente, los filtros no se prueban individualmente, sino como parte de una tabla de filtros, que es una clase genérica que crea el método <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601.CreateFilterTable%2A>.  
  
 Los diversos tipos de filtros se especializan en coincidir con un tipo determinado de condición booleana. Una vez que construye un filtro, no puede cambiar los criterios que utiliza el filtro; para modificar el criterio de un filtro, construya un nuevo y elimine el filtro existente.  
  
### <a name="action-filters"></a>Filtros de acción  
 El <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> contiene una lista de cadenas de acción. Si cualquiera de las acciones en lista de filtros coincide con el encabezado Action en el mensaje o búfer del mensaje, el método `Match` devuelve `true`. Si la lista está vacía, el filtro se considera como un filtro que coincide con todo y cualquier mensaje o búfer del mensaje coincide y `Match` devuelve `true`. Si ninguna de las acciones de lista de filtros coincide con el encabezado Action en el mensaje o búfer del mensaje, el método `Match` devuelve `false`. Si no hay ninguna acción en el mensaje y la lista de filtros no está vacía, `Match` devuelve `false`.  
  
### <a name="endpoint-address-filters"></a>Filtros de dirección de punto de conexión  
 El <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> filtra los mensajes y búferes de mensajes basándose en una dirección de extremo, tal y como se representa en su colección de encabezados. Para que un mensaje pase un filtro de este tipo, se deben cumplir las condiciones siguientes:  
  
- El Identificador uniforme de recursos (URI) de la dirección del filtro debe ser la misma que la del mensaje del encabezado To.  
  
- Cada parámetro de punto de conexión en la dirección del filtro (colección`address.Headers`) debe encontrar un encabezado en el mensaje para realizar la asignación. Los encabezados adicionales en el mensaje o búfer del mensaje son aceptables para que la coincidencia siga siendo `true`.  
  
### <a name="prefix-endpoint-address-filters"></a>Filtros de direcciones de puntos de conexión de prefijos  
  
1. Las funciones <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> como el filtro <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>, solo que la coincidencia puede estar en un prefijo del URI del mensaje. Por ejemplo, un filtro que especifica la dirección `http://www.adatum.com` coincide con los mensajes dirigidos a `http://www.adatum.com/userA`.  
  
### <a name="xpath-message-filters"></a>Filtros de mensajes XPath  
 Un <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> utiliza una expresión XPath para determinar si un documento XML contiene elementos concretos, atributos, texto u otras construcciones sintácticas de XML. El filtro se optimiza para ser extremadamente eficaz para un subconjunto estricto de XPath. El lenguaje de rutas XML se describe en la [especificación W3C XML Path language 1,0](https://www.w3.org/TR/xpath/all/).  
  
 Normalmente, una aplicación usa un <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> en un extremo para consultar el contenido de un mensaje SOAP y, a continuación, realiza las acciones apropiadas en función de los resultados de esa consulta. Un proceso de cola, por ejemplo, puede utilizar una consulta de XPath para inspeccionar el elemento de prioridad de un encabezado conocido para decidir si poner un mensaje al principio de la cola.  
  
## <a name="filter-tables"></a>Tablas de filtros  
 Las tablas de filtros se utilizan para almacenar los pares clave-valor, donde un filtro es la clave y algunos datos asociados son el valor. Los datos de filtros se pueden usar para indicar qué acciones emprender si un mensaje coincide con el filtro y el tipo de los datos de filtro es el parámetro genérico para la clase de la tabla de filtros. Los datos del filtro pueden estar compuestos de reglas de enrutamiento, estado de seguridad de la sesión, agentes de escucha en un canal, etc. Se pueden utilizar los datos donde es necesario el control de flujo de datos.  
  
 Las tablas de filtro implementan la interfaz genérica <xref:System.ServiceModel.Dispatcher.IMessageFilterTable%601>.  
  
 Las tablas de filtro tienen varios métodos que coinciden con un mensaje frente a todos los filtros de la tabla y devuelven una colección no ordenada de datos o filtros coincidentes. Algunos de los métodos de coincidencia son de múltiple coincidencia y devuelven todos los elementos coincidentes. Otros son de coincidencia única, y solo devuelven un elemento, y producen una <xref:System.ServiceModel.Dispatcher.MultipleFilterMatchesException> si más de un filtro coincide.  
  
### <a name="message-filter-table"></a>Tabla de filtros de mensajes  
 La <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> es la implementación más general de <xref:System.ServiceModel.Dispatcher.IMessageFilterTable%601>. Puede almacenar filtros de todos los tipos en la tabla.  
  
 Puede asignar prioridades numéricas a los filtros, donde el mayor número representa la prioridad máxima. Varios tipos de filtros pueden tener la misma prioridad. Un tipo determinado de filtro puede aparecer en más de un nivel de prioridad.  
  
 La coincidencia se realiza comenzando con la máxima prioridad y una vez que se encuentran filtros coincidentes con una prioridad determinada, no se examina ningún filtro con prioridad inferior. Por consiguiente, si está utilizando un método de coincidencia de filtro único, y más de un filtro coincide con un mensaje, pero cada filtro coincidente tiene una prioridad diferente, no se producirá ninguna excepción y se devolverá el filtro con la prioridad más alta. De manera similar, un método de coincidencia de múltiples filtros devuelve solo esos filtros coincidentes con la prioridad más alta.  
  
### <a name="xpath-message-filter-table"></a>Tabla de filtros de mensajes de XPath  
 La <xref:System.ServiceModel.Dispatcher.XPathMessageFilterTable%601> se optimiza para los filtros de XPath declarativos, por lo que la clave de la tabla es <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.  
  
 La clase <xref:System.ServiceModel.Dispatcher.XPathMessageFilterTable%601> optimiza la coincidencia para un subconjunto de XPath que cubre la mayoría de los escenarios de mensajería y también admite la gramática completa de XPath 1.0. Ha optimizado los algoritmos para una coincidencia paralela eficaz.  
  
 Esta tabla tiene varios métodos `Match` especializados que funcionan sobre un <xref:System.Xml.XPath.XPathNavigator> y un <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator>. Un <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> extiende la clase <xref:System.Xml.XPath.XPathNavigator> agregando una propiedad <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator.CurrentPosition%2A>. Esta propiedad permite guardar las posiciones del documento XML y cargarlas rápidamente sin tener que clonar el explorador, una asignación de gran consumo de memoria que <xref:System.Xml.XPath.XPathNavigator> requiere para este tipo de operación. El motor XPath de WCF debe grabar con frecuencia la posición del cursor en el transcurso de la ejecución de consultas en documentos XML, por lo que el <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> proporciona una optimización importante para el procesamiento de mensajes.  
  
## <a name="customer-scenarios"></a>Escenarios de cliente  
 Puede utilizar el filtrado siempre que desee enviar un mensaje a módulos de procesamiento diferentes en función de los datos contenidos en el mensaje. Dos escenarios típicos enrutan un mensaje en función de su código de acción y demultiplexan una secuencia de mensajes en función de la dirección del extremo de los mensajes.  
  
### <a name="routing"></a>Enrutamiento  
 El agente de escuchas de un extremo realiza escuchas para los mensajes que tienen un o más códigos de acción en el encabezado SOAP del mensaje. Esto se implementa mediante la creación de un <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> pasando una matriz que contenga los códigos de acción a su constructor. Utiliza ese filtro para registrarse con el `ListenerFactory`, de modo que solo los mensajes cuya acción coincida con uno de aquéllos en el filtro lleguen a ese extremo concreto.  
  
### <a name="de-multiplexing"></a>Demultiplexación  
 Cuando varios puntos de conexión abanican se extienden fuera del mismo `ServiceListener` fuera de la conexión, la única manera de demultiplexar los mensajes y saber si pertenecen a una cierta dirección del punto de conexión, consiste en utilizar <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>s que seleccionen mensajes hacia los puntos de conexión registrados mediante una búsqueda en la información almacenada en los encabezados. En estos filtros, solo aquellos mensajes que pasan tienen todos los encabezados necesarios que corresponden a ambos:  
  
- El URI en la `EndpointAddress`.  
  
- El resto de los parámetros de extremo en la `EndpointAddress` tal y como se especifica en el <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>.  
  
## <a name="see-also"></a>Vea también

- [Transferencia y serialización de datos](../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
