---
title: Filtros de mensajes
ms.date: 03/30/2017
helpviewer_keywords:
- routing [WCF], message filters
ms.assetid: cb33ba49-8b1f-4099-8acb-240404a46d9a
ms.openlocfilehash: a953dea9224d75907c593d87f06a0b0888f0af2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184661"
---
# <a name="message-filters"></a>Filtros de mensajes
Para implementar el enrutamiento basado en contenido, el servicio de enrutamiento usa implementaciones de <xref:System.ServiceModel.Dispatcher.MessageFilter> que inspeccionan secciones concretas de un mensaje, como la dirección, el nombre del extremo o una instrucción Xpath concreta. Si ninguno de los filtros de mensajes proporcionados con [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] satisface sus necesidades, puede crear un filtro personalizado creando una nueva implementación de la clase base <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 Al configurar el servicio de enrutamiento,<xref:System.ServiceModel.Routing.Configuration.FilterElement> debe definir elementos de filtro (objetos) que describan el tipo de **MessageFilter** y los datos auxiliares necesarios para crear el filtro, como valores de cadena específicos para buscar dentro del mensaje. Tenga en cuenta que, al crear los elementos del filtro, solo se definen los filtros de mensajes individuales; para usar los filtros para evaluar y enrutar mensajes, también deberá definir una tabla de filtros (<xref:System.ServiceModel.Routing.Configuration.FilterTableEntryCollection>).  
  
 Cada entrada de la tabla de filtros hace referencia a un elemento del filtro y especifica el extremo de cliente al que se enrutará un mensaje si éste coincide con el filtro. Las entradas de la tabla de filtros también le permiten especificar una recopilación de puntos de conexión de reserva (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>), que definen una lista de puntos de conexión a los que se transmitirá el mensaje en caso de fallo de transmisión al realizar un envío al punto de conexión primario. Estos puntos de conexión se probarán en el orden especificado hasta que uno se realice correctamente.  
  
## <a name="message-filters"></a>Filtros de mensajes  
 Los filtros de mensajes usados por el servicio de enrutamiento proporcionan una funcionalidad de selección de mensaje común, como evaluar el nombre del extremo al que se ha enviado un mensaje, la acción SOAP, o la dirección o prefijo de dirección al que se ha enviado el mensaje. Los filtros también pueden estar unidos a una condición `AND`, de manera que los mensajes solo se enruten a un extremo si el mensaje coincide con ambos filtros. También puede crear filtros personalizados creando su propia implementación de <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 La siguiente tabla muestra la enumeración <xref:System.ServiceModel.Routing.Configuration.FilterType> usada por el servicio de enrutamiento, la clase que implementa el filtro de mensajes concreto, así como los parámetros <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A> necesarios.  
  
|Tipo de filtro|Descripción|Significado de datos del filtro|Ejemplo de filtro|  
|------------------|-----------------|-------------------------|--------------------|  
|Acción|Utiliza la clase <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> para coincidir con mensajes que contienen una acción concreta.|La acción según la cual se va a filtrar.|\<nombre del filtro "action1" filterType -"Action" filterData""http://namespace/contract/operation" />|  
|EndpointAddress|Utiliza <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> la clase, con <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` para hacer coincidir los mensajes que contienen una dirección específica.|La dirección según la cual se va a filtrar (en el encabezado To).|\<nombre del filtro "dirección1" filterType -"EndpointAddress" filterData"http://host/vdir/s.svc/b" />|  
|EndpointAddressPrefix|Utiliza <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> la clase, con <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` para hacer coincidir los mensajes que contienen un prefijo de dirección específico.|La dirección según la cual se va a filtrar que usa la coincidencia de prefijo más larga.|\<nombre del filtro "prefijo1" filterType -"EndpointAddressPrefix" filterData"http://host/" ">|  
|And|Utiliza la clase <xref:System.ServiceModel.Dispatcher.StrictAndMessageFilter>, que siempre evalúa ambas condiciones antes de realizar la devolución.|filterData no se utiliza; en su lugar filter1 y filter2 tienen los nombres de los filtros de mensajes correspondientes (también en la tabla), que deben ser **AND**ed juntos.|\<nombre del filtro "y 1" filterType "Y" filter1"address1" filter2"action1" />|  
|Personalizado|Tipo definido por el usuario que extiende la clase <xref:System.ServiceModel.Dispatcher.MessageFilter> y tiene un constructor que toma una cadena.|El atributo customType es el nombre del tipo completo de la clase que se va a crear; filterData es la cadena que se va a pasar al constructor al crear el filtro.|\<nombre del filtro "custom1" filterType "CustomType" customType"CustomAssembly.CustomMsgFilter, CustomAssembly" filterData"Custom Data" />|  
|EndpointName|Utiliza la clase <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> para coincidir con mensajes en función del nombre del punto de conexión de servicio al que llegaron.|El nombre del punto de conexión de servicio, por ejemplo: "serviceEndpoint1".  Debería ser uno de los extremos expuestos en el servicio de enrutamiento.|\<nombre del filtro "stock1" filterType "Endpoint" filterData"SvcEndpoint" />|  
|MatchAll|Utiliza la clase <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>. Este filtro coincide con todos los mensajes entrantes.|No se usa filterData. Este filtro siempre coincide con todos los mensajes.|\<nombre del filtro "matchAll1" filterType"MatchAll" />|  
|XPath|Utiliza la clase <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> para coincidir con consultas XPath concretas dentro del mensaje.|Consulta XPath que se va a usar al realizar la coincidencia de mensajes.|\<nombre del filtro "XPath1" filterType "XPath" filterData"//ns:element" />|  
  
 En el siguiente ejemplo, se definen entradas de filtro que usan los filtros de mensajes XPath, EndpointName y PrefixEndpointAddress. Este ejemplo también muestra cómo utilizar un filtro personalizado para las entradas de RoundRobinFilter1 y RoundRobinFilter2.  
  
```xml  
<filters>  
     <filter name="XPathFilter" filterType="XPath"
             filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
     <filter name="EndpointNameFilter" filterType="EndpointName"
             filterData="calculatorEndpoint"/>  
     <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"
             filterData="http://localhost/routingservice/router/rounding/"/>  
     <filter name="RoundRobinFilter1" filterType="Custom"
             customType="RoutingServiceFilters.RoundRobinMessageFilter,
             RoutingService" filterData="group1"/>  
     <filter name="RoundRobinFilter2" filterType="Custom"
             customType="RoutingServiceFilters.RoundRobinMessageFilter,
             RoutingService" filterData="group1"/>  
</filters>  
```  
  
> [!NOTE]
> El hecho de definir un filtro no hace que los mensajes se evalúen según dicho filtro. El filtro se debe agregar a una tabla de filtros, que, posteriormente, se asocia al punto de conexión de servicio expuesto por el servicio de enrutamiento.  
  
### <a name="namespace-table"></a>Tabla de espacio de nombres  
 Al utilizar un filtro XPath, los datos del filtro que contienen la consulta XPath pueden resultar sumamente grandes debido al uso de espacios de nombres. Para reducir este problema, el servicio de enrutamiento proporciona la capacidad de definir sus propios prefijos de espacio de nombres utilizando la tabla de espacio de nombres.  
  
 La tabla de espacio de nombres es una colección de objetos <xref:System.ServiceModel.Routing.Configuration.NamespaceElement> que define los prefijos de espacio de nombres para los espacios de nombres comunes que se pueden utilizar en un XPath. A continuación, se muestran espacios de nombres y prefijos de espacio de nombres predeterminados incluidos en la tabla de espacio de nombres.  
  
|Prefijo|Espacio de nombres|  
|------------|---------------|  
|s11|`http://schemas.xmlsoap.org/soap/envelope`|  
|s12|`http://www.w3.org/2003/05/soap-envelope`|  
|wsaAugust2004|`http://schemas.xmlsoap.org/ws/2004/08/addressing`|  
|wsa10|`http://www.w3.org/2005/08/addressing`|  
|sm|`http://schemas.microsoft.com/serviceModel/2004/05/xpathfunctions`|  
|tempuri|`http://tempuri.org`|  
|ser|`http://schemas.microsoft.com/2003/10/Serialization`|  
  
 Si sabe que va a usar un espacio de nombres concreto en sus consultas de XPath, puede agregarlo a la tabla de espacio de nombres junto con un prefijo de espacio de nombres único y utilizar dicho prefijo en cualquier consulta XPath en lugar del espacio de nombres completo. En el ejemplo siguiente se define un `"http://my.custom.namespace"`prefijo de "custom" para el espacio de nombres, que se usa en la consulta XPath contenida en filterData.  
  
```xml  
<namespaceTable>  
     <add prefix="custom" namespace="http://my.custom.namespace/"/>  
</namespaceTable>  
<filters>  
     <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
</filters>  
```  
  
## <a name="filter-tables"></a>Tablas de filtros  
 Aunque cada elemento del filtro define una comparación lógica que se puede aplicar a un mensaje, la tabla de filtros proporciona la asociación entre el elemento del filtro y el extremo de cliente de destino. Una tabla de filtros es una recopilación ordenada de objetos <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement> que define la asociación entre un filtro, un extremo de destino primario y una lista de extremos de reserva alternativos. Las entradas de la tabla de filtros también le permiten especificar una prioridad opcional para cada condición de filtro. El siguiente ejemplo define dos filtros y, a continuación, define una tabla de filtros que asocia cada filtro a un punto de conexión de destino.  
  
```xml  
<routing>  
     <filters>  
       <filter name="AddAction" filterType="Action" filterData="Add" />  
       <filter name="SubtractAction" filterType="Action" filterData="Subtract" />  
     </filters>  
     <filterTables>  
       <table name="routingTable1">  
         <filters>  
           <add filterName="AddAction" endpointName="Addition" />  
           <add filterName="SubtractAction" endpointName="Subtraction" />  
         </filters>  
       </table>  
     </filterTables>
</routing>  
```  
  
### <a name="filter-evaluation-priority"></a>Prioridad de la evaluación de filtros  
 Todas las entradas de la tabla de filtros se evalúan simultáneamente de forma predeterminada, y el mensaje que se evalúa se enruta a los extremos asociados a cada entrada de filtro coincidente. Si varios filtros se evalúan como `true`, y el mensaje es unidireccional o dúplex, el mensaje se transmite por multidifusión a los puntos de conexión de todos los filtros coincidentes. Los mensajes solicitud-respuesta no se pueden transmitir por multidifusión porque solo se puede devolver una respuesta al cliente.  
  
 Puede implementarse una lógica de enrutamiento más compleja especificando niveles de prioridad para cada filtro; el servicio de enrutamiento evalúa primero todos los filtros del nivel de prioridad máxima. Si un mensaje coincide con un filtro de este nivel, no se procesa ningún filtro con una prioridad menor. Por ejemplo, un mensaje unidireccional de entrada se evalúa primero con respecto a todos los filtros con prioridad 2. El mensaje no coincide con ningún filtro en este nivel de prioridad, así que, a continuación, el mensaje se compara con los filtros con prioridad 1. Dos filtros de prioridad 1 coinciden con el mensaje y, como es un mensaje unidireccional, se enruta a ambos puntos de conexión de destino.  Dado que se ha detectado una coincidencia en los filtros de prioridad 1, no se evalúa ningún filtro de prioridad 0.  
  
> [!NOTE]
> Si no se especifica ninguna prioridad, se usa la prioridad 0 predeterminada.  
  
 En el siguiente ejemplo, se define una tabla de filtros que especifica prioridades 2, 1 y 0 para los filtros indicados en la tabla.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="XPathFilter" endpointName="roundingCalcEndpoint"
               priority="2"/>  
          <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint"
               priority="1"/>  
          <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint"
               priority="1"/>  
          <add filterName="MatchAllMessageFilter" endpointName="defaultCalcEndpoint"
               priority="0"/>  
     </filterTable>  
</filterTables>  
```  
  
 En el ejemplo anterior, si un mensaje coincide con XPathFilter, se enrutará a roundingCalcEndpoint y no se evaluará ningún filtro más en la tabla porque todos los demás filtros tienen una prioridad menor. Sin embargo, si el mensaje no coincide con XPathFilter, se evaluará con respecto a todos los filtros de prioridad inmediatamente inferior, EndpointNameFilter y PrefixAddressFilter.  
  
> [!NOTE]
> Cuando sea posible, utilice filtros exclusivos en lugar de especificar una prioridad, ya que la evaluación de la prioridad puede producir una reducción del rendimiento.  
  
### <a name="backup-lists"></a>Listas de reserva  
 Cada filtro de la tabla de filtros puede especificar opcionalmente una lista de reserva, que es una recopilación ordenada de puntos de conexión (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>). Esta colección contiene una lista ordenada de puntos de conexión a los que se transmitirá el mensaje en caso de <xref:System.ServiceModel.CommunicationException> durante un envío al punto de conexión primario especificado en <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.EndpointName%2A>. En el ejemplo siguiente se define una lista de copia de seguridad denominada "backupServiceEndpoints" que contiene dos puntos de conexión.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
 En el ejemplo anterior, si se produce un error en un envío al punto de conexión principal "Destino", el servicio de enrutamiento intentará enviar a cada extremo de la secuencia en la que se enumeran, primero enviando a backupServiceQueue y, posteriormente, enviando a alternateServiceQueue si el se produce un error en backupServiceQueue. Si se produce un error en todos los puntos de conexión de reserva, se devuelve un error.
