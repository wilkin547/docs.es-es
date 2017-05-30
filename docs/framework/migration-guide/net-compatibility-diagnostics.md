---
title: "Diagnósticos de compatibilidad de .NET | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: twsouthwick
ms.author: tasou
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 06ebf87e02c8fd745d9c2f3a55eca329323a7d91
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="net-compatibility-diagnostics"></a>Diagnósticos de compatibilidad de .NET
Los diagnósticos de compatibilidad de .NET son analizadores de Roslyn que ayudan a identificar problemas de compatibilidad de aplicaciones entre versiones de .NET Framework. Esta lista contiene todos los analizadores disponibles, aunque solo se aplicará un subconjunto de ellos a una migración determinada. Los analizadores determinarán qué problemas son aplicables para la migración planeada y serán los únicos que muestren. Para ver los problemas divididos por las versiones a las que afectan, consulte [Compatibilidad de aplicaciones en .NET Framework](../../../docs/framework/migration-guide/application-compatibility.md).  
  
 Cada problema incluye la siguiente información:  
  
-   La descripción de los cambios con respecto a una versión anterior.  
  
-   La sugerencia, que es una descripción de cómo afecta el cambio a los clientes e indica si hay alguna solución alternativa disponible para mantener la compatibilidad entre versiones.  
  
-   Una valoración de la importancia que tiene el cambio. Los problemas de compatibilidad de aplicaciones se dividen en las siguientes categorías:  
  
    |||  
    |-|-|  
    |Major|Un cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.|  
    |Secundaria|Un cambio que afecta a un pequeño número de aplicaciones o que requiere una leve modificación del código.|  
    |Caso avanzado|Un cambio que afecta a aplicaciones en situaciones muy concretas y poco frecuentes.|  
    |Transparente|Un cambio que no tiene ningún efecto apreciable para el desarrollador o el usuario de la aplicación.|  
  
-   La versión, que indica la primera aparición del cambio en .NET Framework. Se revierten algunos de los cambios, lo que también se indica.  
  
-   El tipo de cambio:  
  
    |||  
    |-|-|  
    |Redestinación|El cambio afecta a aplicaciones que se vuelven a compilar para tener como destino una nueva versión de .NET Framework.|  
    |Tiempo de ejecución|El cambio afecta a una aplicación existente que tiene como destino una versión anterior de .NET Framework, pero que se ejecuta en una versión posterior.|  
  
-   Las API afectadas, si las hubiera.  
  
-   Los identificadores de los diagnósticos disponibles.  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares  
  
|||  
|-|-|  
|Detalles|SoapFormatter no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión diferente. En concreto, en algunas colecciones ordenadas (como Hashtable) se agregaron miembros entre las versiones 4.0 y 4.5 respecto a los cuales no es posible efectuar la deserialización de objetos con .NET 4.0 si se serializaron con .NET 4.5. Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.|  
|Sugerencia|La serialización realizada con SoapFormatter debe reemplazarse por una serialización de BinaryFormatter o NetDataContractSerialization para resistir los cambios de .NET Framework.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|Analizadores|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: Los elementos DataTemplate de WPF ahora son visibles en la UIA  
  
|||  
|-|-|  
|Detalles|Anteriormente, los elementos DataTemplate no eran visibles para la automatización de la IU. A partir de la versión 4.5, la automatización de la IU detectará estos elementos. Esta característica resulta útil en muchos casos, pero puede interrumpir pruebas que dependan de árboles de la UIA que no contengan elementos DataTemplate.|  
|Sugerencia|Puede ser necesario actualizar las pruebas de automatización de la IU para esta aplicación con el fin de procesar el árbol de la UIA que ahora incluye elementos DataTemplate que antes no eran visibles. Por ejemplo, en aquellas pruebas en las que se espere que haya ciertos elementos contiguos entre sí, ahora puede ser necesario esperar ciertos elementos intermedios de la UIA que antes no eran visibles. También puede ser necesario actualizar con nuevos valores pruebas que dependan de ciertos recuentos o índices para elementos de la UIA.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|Analizadores|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: El texto seleccionado de un cuadro de texto de WPF aparece en un color diferente cuando el cuadro de texto esté inactivo  
  
|||  
|-|-|  
|Detalles|En .NET 4.5, cuando un control de cuadro de texto de WPF esté inactivo (sin el foco), el texto seleccionado dentro del cuadro aparecerá en un color diferente al que lo haría con el control activo.|  
|Sugerencia|Es posible restaurar el comportamiento anterior (.NET 4.0) estableciendo la propiedad [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) como false.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analizadores|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List\<T>.ForEach puede iniciar una excepción al modificar un elemento de lista  
  
|||  
|-|-|  
|Detalles|A partir de .NET 4.5, los enumeradores `List<T>.ForEach` inician una excepción InvalidOperationException si se modifica algún elemento de la colección que realiza la llamada. En versiones anteriores no se iniciaban excepciones en estos casos, aunque sí podían producirse condiciones de carrera.|  
|Sugerencia|Lo ideal es corregir el código para no modificar listas durante la enumeración de sus elementos, ya que esta nunca es una operación segura. No obstante, para revertir al comportamiento anterior, es posible seleccionar .NET 4.0 como destino de una aplicación.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|Analizadores|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: El análisis System.Uri cumple con las disposiciones de RFC 3987  
  
|||  
|-|-|  
|Detalles|El análisis de identificadores URI se ha modificado de diferentes formas en .NET 4.5. No obstante, estos cambios solo afectan al código que tenga como destino .NET 4.5. Si hubiera algún binario que tuviera como destino .NET 4.0, presentaría el comportamiento anterior. Entre los cambios efectuados en el análisis de identificadores URI en .NET 4.5 se incluyen los siguientes:<br /><br /> Los análisis de identificadores URI efectuarán comprobaciones de normalización y caracteres conforme a las normas más recientes sobre IRI indicadas en RFC 3987.<br /><br /> La forma de normalización C de Unicode solo se ejecutará en la sección del host del identificador URI.<br /><br /> Los identificadores URI de mailto: no válidos ahora provocarán una excepción.<br /><br /> Los puntos finales del final de un segmento de trazado ahora se conservarán.<br /><br /> Los identificadores URI de `file://` no aplican secuencias de escape al carácter `?`.<br /><br /> Los caracteres de control Unicode `U+0080` a `U+009F` no son compatibles.<br /><br /> A los caracteres de coma `,` y `%2c` no se les eliminan automáticamente las secuencias de escape.|  
|Sugerencia|Si es necesario usar la anterior semántica de análisis de identificadores URI de .NET 4.0 (lo que no es habitual), puede usarse eligiendo .NET 4.0 como destino. Puede hacerse usando un atributo TargetFrameworkAttribute en el ensamblado, o bien a través de la IU del sistema del proyecto de Visual Studio, en la página "Propiedades del proyecto".|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|Analizadores|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: El System.Uri de escape ahora es compatible con RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|Detalles|La aplicación de secuencias de escape a los identificadores URI se ha modificado en .NET 4.5 para hacerlo compatible con [RFC 3986](http://tools.ietf.org/html/rfc3986). Cambios concretos:<br /><br /> El método `EscapeDataString` incluye los caracteres reservados entre caracteres de escape de con arreglo a RFC 3986.<br /><br /> El método `EscapeUriString` no incluye entre caracteres de escape los caracteres reservados.<br /><br /> El método `UnescapeDataString` no inicia una excepción si encuentra una secuencia de escape no válida.<br /><br /> Los caracteres de escape no reservados no se incluyen en una secuencia de escape.|  
|Sugerencia|Las aplicaciones de actualización no deben basarse en UnescapeDataString para iniciarse en caso de tratarse de secuencias de escape no válidas. Ahora, este tipo de secuencias deben detectarse directamente.<br /><br /> De igual modo, cabe esperar que los identificadores URI y las cadenas de datos con secuencias de escape y sin ellas varíen entre .NET 4.0 y .NET 4.5, y no deben compararse directamente entre distintas versiones de .NET. En lugar de ello, deben analizarse y normalizarse en una única versión de .NET antes de efectuar cualquier comparación.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|Analizadores|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: System.Net.PeerToPeer.Collaboration no disponible en Windows 8  
  
|||  
|-|-|  
|Detalles|El espacio de nombres System.Net.PeerToPeer.Collaboration no está disponible en Windows 8 o posterior.|  
|Sugerencia|Es necesario actualizar las aplicaciones compatibles con Windows 8 o posterior para no depender de este espacio de nombres ni sus miembros.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|Analizadores|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: Los catálogos de MEF implementan IEnumerable y, por tanto, ya no pueden usarse para crear un serializador  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, los catálogos de MEF implementan IEnumerable y, por tanto, ya no pueden usarse para crear un serializador (objeto XmlSerializer). Al intentar serializar un catálogo de MEF se inicia una excepción.|  
|Sugerencia|Ya no se puede usar MEF para crear un serializador.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: La ausencia de moniker de la versión de .NET Framework de destino da lugar a un comportamiento de la versión 4.0  
  
|||  
|-|-|  
|Detalles|Las aplicaciones sin un elemento [TargetFrameworkAttribute](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) aplicado en el nivel de ensamblado se ejecutarán automáticamente conforme a la semántica (peculiaridades) de .NET Framework 4.0. Para garantizar una buena calidad, se recomienda que todos los binarios incluyan un atributo explícito TargetFrameworkAttribute en el que se indique la versión de .NET Framework con la que se compilaron. Tenga en cuenta que usar un moniker de la versión de .NET Framework de destino en un archivo del proyecto hará que MSBuild aplique automáticamente un elemento TargetFrameworkAttribute.|  
|Sugerencia|Debe incluirse un [atributo de la versión de .NET Framework de destino](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) agregando el atributo directamente al ensamblado, especificando una versión de .NET Framework de destino en el [archivo del proyecto, o bien a través de la GUI de propiedades del proyecto de Visual Studio](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: Ya no se puede establecer EnableViewStateMac como false  
  
|||  
|-|-|  
|Detalles|ASP.NET ya no permite a los desarrolladores especificar `<pages enableViewStateMac="false"/>` o `<@Page EnableViewStateMac="false" %>`. El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado. Solo afecta a aquellas aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente como false.|  
|Sugerencia|Se debe suponer que EnableViewStateMac está establecido como true y es necesario resolver cualquier error de MAC resultante (como se explica en [esta](https://support.microsoft.com/kb/2915218) guía, que contiene diversas resoluciones dependientes de la causa específica de los errores de MAC).|  
|Ámbito|Major|  
|Versión|4.5.2|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection\<T>.TryTakeFromAny deja de iniciarse  
  
|||  
|-|-|  
|Detalles|Si alguna de las colecciones de entrada está marcada como completada, `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` no devuelve -1 y `BlockingCollection<T>.TakeFromAny` deja de iniciar una excepción. Este cambio permite trabajar con colecciones cuando una de las colecciones está vacía o completa y la otra colección todavía tiene elementos que se pueden recuperar.|  
|Sugerencia|Si se han usado un método TryTakeFromAny que devuelva -1 o un método TakeFromAny de inicio para el control de flujo en casos en los que se complete una recolección de bloqueo, es necesario cambiar dicho código para que use `.Any(b => b.IsCompleted)` para detectar dicha condición.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analizadores|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException ahora establece correctamente las posiciones de las líneas  
  
|||  
|-|-|  
|Detalles|Si se pasa el valor LoadOptions.SetLineInfo al método Load y se produce un error de validación, las propiedades XmlSchemaException.LineNumber y XmlSchemaException.LinePosition pasan a contener información sobre las líneas.|  
|Sugerencia|Debería actualizarse el código de control de excepciones que suponga que no van a establecerse las propiedades XmlSchemaException.LineNumber ni XmlSchemaException.LinePosition, ya que, ahora, estas se establecerán correctamente al usar el valor SetLineInfo durante la carga de XML.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=fullName>|  
|Analizadores|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities pasa a ser APTCA  
  
|||  
|-|-|  
|Detalles|El ensamblado está marcado con el atributo AllowPartiallyTrustedCallersAttribute.|  
|Sugerencia|Las clases derivadas no se pueden marcar con el atributo SecurityCriticalAttribute. Anteriormente, era necesario marcar los tipos derivados con el atributo SecurityCriticalAttribute. Sin embargo, este cambio no debería tener ningún impacto.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: Los tipos de WorkFlow 3.0 están obsoletos  
  
|||  
|-|-|  
|Detalles|Las API de Windows Workflow Foundation (WWF) 3.0 (las procedentes del espacio de nombres System.Workflow) ahora están obsoletas.|  
|Sugerencia|En su lugar, deben usarse nuevas API de WWF 4.0 (en System.Activities). Puede encontrar un ejemplo de uso de las nuevas API [aquí](https://msdn.microsoft.com/library/jj205427.aspx). Hay disponible más información [aquí](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx). Además, las API de WWF 3.0 continúan siendo compatibles, por lo que pueden seguir usándose. También se puede evitar la advertencia de tiempo de compilación suprimiéndola o usando un compilador anterior.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Redestinación|  
|Analizadores|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: Algunas API de arrastrar y colocar del flujo de trabajo están obsoletas  
  
|||  
|-|-|  
|Detalles|Esta API de arrastrar y colocar del flujo de trabajo está obsoleta y genera advertencias del compilador si la aplicación se vuelve a compilar en 4.5.|  
|Sugerencia|En su lugar, deben usarse nuevas API [DragDropHelper](https://msdn.microsoft.com/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) compatibles con operaciones con varios objetos. También es posible suprimir las advertencias de compilación o usar un compilador anterior para evitarlas. Las API siguen siendo compatibles.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|Analizadores|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: Las nuevas sobrecargas (ambiguas) de Dispatcher.Invoke pueden dar pie a un comportamiento diferente  
  
|||  
|-|-|  
|Detalles|.NET Framework 4.5 agrega nuevas sobrecargas para Dispatcher.Invoke, entre las que se incluye un parámetro de tipo System.Action. Cuando el código existente se vuelve a compilar, los compiladores pueden resolver llamadas a métodos Dispatcher.Invoke que tienen un parámetro Delegate como llamadas a métodos Dispatcher.Invoke con un parámetro System.Action. Si una llamada a una sobrecarga Dispatcher.Invoke con un parámetro Delegate se resuelve como una llamada a una sobrecarga Dispatcher.Invoke con un parámetro System.Action, pueden producirse las siguientes diferencias de comportamiento:<br /><br /> Si se produce una excepción, no se generan eventos Dispatcher.UnhandledExceptionFilter ni Dispatcher.UnhandledException. En lugar de ello, las excepciones se controlan mediante el evento UnobservedTaskException.<br /><br /> Las llamadas a algunos miembros, como DispatcherOperation.Result, se bloquean hasta que se completa la operación.|  
|Sugerencia|Para evitar ambigüedades (y posibles diferencias en el control de excepciones o los comportamientos de bloqueo), el código que llame a Dispatcher.Invoke puede pasar un objeto vacío [] como segundo parámetro de la llamada Invoke para garantizar que la resolución se resuelva en la sobrecarga del método de .NET 4.0.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|Analizadores|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: El constructor EncoderParameter está obsoleto  
  
|||  
|-|-|  
|Detalles|El constructor `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` está obsoleto e introducirá advertencias de compilación si se usa.|  
|Sugerencia|Aunque el constructor `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` continúa funcionado, en lugar de él se debe usar el siguiente constructor a fin de evitar la advertencia de compilación obsoleta al volver a compilar código con las herramientas de .NET 4.5: [EncoderParameter.EncoderParameter(Encoder, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/library/hh875096\(v=vs.110\).aspx).|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analizadores|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: Cambio de comportamiento para los métodos Task.WaitAll con argumentos de tiempo de espera  
  
|||  
|-|-|  
|Detalles|El comportamiento de Task.WaitAll se ha hecho más coherente en .NET 4.5.<br /><br /> En .NET Framework 4, estos métodos se comportaban de forma incoherente. Cuando se agotaba el tiempo de espera, si una o varias tareas se completaban o cancelaban antes de la llamada al método, el método producía una excepción AggregateException. Cuando se agotaba el tiempo de espera, si no se completaba ni cancelaba ninguna tarea antes de la llamada al método, pero una o varias tareas entraban en estos estados después de la llamada al método, el método pasaba a ser false.<br />En .NET Framework 4.5, estas sobrecargas de método ahora pasan a ser false si las tareas siguen en ejecución cuando se agota el intervalo de tiempo de espera y producen una excepción AggregateException solo si se ha cancelado una tarea de entrada (independientemente de si se canceló antes o después de la llamada al método) y no hay ninguna tarea en ejecución.|  
|Sugerencia|Si se detectó una excepción AggregateException como medio de detección de una tarea cancelada antes de invocar la llamada WaitAll, es necesario que el código, en lugar de ello, realice la misma detección mediante la propiedad IsCanceled (por ejemplo, .Any(t => t.IsCanceled)), ya que .NET 4.6 solo se iniciará en este caso si todas las tareas esperadas se completan antes de que se agote el tiempo de espera.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analizadores|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: Cambio de comportamiento en las API de lenguaje de definición de datos (DDL)  
  
|||  
|-|-|  
|Detalles|El comportamiento de las API de DDL cuando se especifica AttachDBFilename ha cambiado tal y como se describe a continuación:<br /><br /> Las cadenas de conexión no necesitan especificar un valor Initial Catalog. Anteriormente, se necesitaban los valores AttatchDBFilename e Initial Catalog.<br /><br /> Si se especifican los valores AttatchDBFilename e Initial Catalog, y existe el archivo MDF indicado, el método ObjectContext.DatabaseExists pasa a ser true. Anteriormente, pasaba a ser false.<br /><br /> Si se especifican los valores AttatchDBFilename e Initial Catalog, y existe el archivo MDF indicado, al llamar al método ObjectContext.DeleteDatabase se eliminan los archivos.<br /><br /> Si se llama al método ObjectContext.DeleteDatabase cuando la cadena de conexión especifica un valor de AttachDBFilename con un archivo MDF que no exista y un valor Initial Catalog que tampoco exista, el método inicia una excepción InvalidOperationException. Anteriormente, iniciaba una excepción SqlException.|  
|Sugerencia|Estos cambios facilitan la creación de herramientas y aplicaciones que utilizan las API de DDL. Estos cambios pueden afectar a la compatibilidad de las aplicaciones en los escenarios siguientes:<br /><br /> El usuario escribe código que ejecuta un comando DROP DATABASE directamente en lugar de llamar al método ObjectContext.DeleteDatabase si ObjectContext.DatabaseExists pasa a ser true. Esto interrumpe el código existente si la base de datos no está asociada pero el archivo MDF existe.<br /><br /> El usuario escribe código que espera que el método ObjectContext.DeleteDatabase inicie una excepción SqlException en lugar de InvalidOperationException cuando el valor Initial Catalog y el archivo MDF no existan.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: Los métodos MachineKey.Encode y MachineKey.Decode ahora están obsoletos  
  
|||  
|-|-|  
|Detalles|Estos métodos están obsoletos. La compilación del código que llama a estos métodos genera una advertencia del compilador.|  
|Sugerencia|Las alternativas recomendadas son [MachineKey.Protect](https://msdn.microsoft.com/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) y [MachineKey.Unprotect](https://msdn.microsoft.com/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx). También es posible suprimir las advertencias de compilación o usar un compilador anterior para evitarlas. Las API siguen siendo compatibles.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> <xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|Analizadores|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: El método Replace de las direcciones URL de OData está deshabilitado de forma predeterminada  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, el método Replace de direcciones URL de OData está deshabilitado de forma predeterminada. Cuando el método Replace de OData esté deshabilitado (ahora, de forma predeterminada), cualquier solicitud de usuario, incluidas las funciones Replace (que son poco frecuentes), generará un error.|  
|Sugerencia|Si es necesario usar el método Replace (lo que es poco frecuente), puede volver a habilitarse mediante una [configuración](https://msdn.microsoft.com/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx). No obstante, si el método Replace está activado, puede crear vulnerabilidades de seguridad y solo debería usarse tras una revisión exhaustiva.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|Analizadores|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: El objeto System.ServiceModel.Web.WebServiceHost ya no agrega un extremo predeterminado  
  
|||  
|-|-|  
|Detalles|El objeto System.ServiceModel.Web.WebServiceHost ya no agrega un extremo predeterminado si ya se ha agregado uno explícito mediante el código de aplicación.|  
|Sugerencia|Si los usuarios esperan poder conectarse a un extremo predeterminado y ya se agregaron otros explícitos a WebServiceHost, también deberían incorporarse extremos predeterminados de forma explícita (mediante elementos AddDefaultEndpoint).|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|Analizadores|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)  
  
|||  
|-|-|  
|Detalles|El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de EventSource que define un método de evento ETW debe llamar al método EventSource.WriteEvent de la clase base con el identificador de evento seguido de los mismos argumentos que se pasaron al método de evento ETW.|  
|Sugerencia|Se inicia una excepción IndexOutOfRangeException si un elemento EventListener lee datos EventSource en proceso para un origen del evento que incumple este contrato.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: El valor MinFreeMemoryPercentageToActiveService ahora se respeta  
  
|||  
|-|-|  
|Detalles|Este ajuste establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF. Está diseñado para evitar excepciones OutOfMemoryException. En .NET Framework 4.5, este ajuste no tenía ningún efecto. En .NET Framework 4.5.1, este ajuste se respeta.|  
|Sugerencia|Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración. Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: La expansión de entidades DTD de la clase XmlTextReader está limitada a 10 000 000 caracteres  
  
|||  
|-|-|  
|Detalles|La expansión de entidades DTD ahora está limitada a 10 000 000 caracteres. La carga de archivos XML sin expansión de entidades DTD o con expansión de entidades DTD limitada no se verá afectada. Los archivos con entidades de DTD que se expanden a más de 10.000.000 caracteres no se podrán cargar y ahora iniciarán una excepción.|  
|Sugerencia|Si el límite de expansión de entidades DTD de 10 000 000 caracteres es demasiado bajo, puede anularse con la propiedad [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx). Es posible pasar un elemento XmlReaderSettings con el valor MaxCharactersFromEntity adecuado a [XmlReader.Create](https://msdn.microsoft.com/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|Analizadores|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: Cambio del mensaje de excepción de la hoja de estilos XSLT  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, el texto del mensaje de error cuando un archivo XSLT es demasiado complejo es "The style sheet is too complex" (La hoja de estilos es demasiado compleja). En versiones anteriores, el mensaje de error era “Error de compilación de XSLT”. El código de aplicación que se base en el texto del mensaje de error ya no funcionará. Sin embargo, los tipos de excepción siguen siendo iguales, por lo que este cambio no debería tener ningún impacto real.|  
|Sugerencia|Actualice cualquier código de aplicación en función del mensaje de la excepción de esta condición de error para que espere el nuevo mensaje, o bien (e incluso mejor), actualice el código para que dependa solo del tipo de excepción ([XsltException](https://msdn.microsoft.com/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)), que no cambió.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|Analizadores|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF ahora serializa el valor Expressions.Literal\<T> DateTimes de forma diferente (interrumpe los analizadores de XAML personalizados)  
  
|||  
|-|-|  
|Detalles|El objeto [ValueSerializer](https://msdn.microsoft.com/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) asociado convertirá aquellos objetos DateTime o DateTimeOffset cuyos componentes de segundos y milisegundos sean distintos de cero, así como aquellos (para un valor DateTime) cuya propiedad DateTime.Kind no esté sin especificar con respecto a la sintaxis de un elemento de propiedad en lugar de a una cadena. Este cambio permite realizar un recorrido de ida y vuelta por los valores DateTime y DateTimeOffset. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.|  
|Sugerencia|Este cambio permite realizar un recorrido de ida y vuelta por los valores DateTime y DateTimeOffset. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: Nuevos valores de enumeración en PageRangeSelection de WPF  
  
|||  
|-|-|  
|Detalles|Se han agregado dos nuevos miembros (CurrentPage y SelectedPage) a la enumeración de [PageRangeSelection](https://msdn.microsoft.com/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx).|  
|Sugerencia|En la mayoría de los casos, estos cambios no afectan al código del usuario. No obstante, debería modificarse el código que dependa de un número particular de elementos existentes en las llamadas Enum.GetNames o Enum.GetValues del tipo PageRangeSelection.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|Analizadores|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: El elemento DispatcherSynchronizationContext.CreateCopy de WPF ahora devuelve una nueva copia en lugar de la instancia actual  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4, el elemento DispatcherSynchronizationContext.CreateCopy() devolvía una referencia a la instancia actual, principalmente a modo de optimización del rendimiento. En .NET Framework 4.5, devuelve una nueva instancia que permite concluir por primera vez que las mismas referencias indican que el subproceso de ejecución se encuentra en el contexto de sincronización correcto.  Es poco probable que el código que comprueba la identidad de estas referencias se vea afectado, pero, debido al cambio, debería probarse el código que llame a DispatcherSynchronizationContext.CreateCopy como parte de una migración a .NET Framework 4.5 o una versión posterior.|  
|Sugerencia|Tenga en cuenta de que DispatcherSynchronizationContext.CreateCopy() ahora devolverá un nuevo objeto SynchronizationContext.  Anteriormente, el código que usaba una equivalencia de referencias generadas de esta forma no comprobaba en realidad si se encontraba en el contexto correcto, pero sí lo hace si se compila en .NET Framework 4.5 o una versión posterior.  Aunque es poco probable que cause problemas, debería bastar con ejecutar las rutas de acceso del código afectado para comprobar si lo hace.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|Analizadores|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: System.Threading.Tasks.Task ya no inicia ObjectDisposedException después de desechar un objeto  
  
|||  
|-|-|  
|Detalles|A excepción de Task.IAsyncResult.AsyncWaitHandle, los métodos System.Threading.Tasks.Task ya no inician una excepción ObjectDisposedException después de desechar el objeto.<br />Este cambio admite el uso de tareas almacenadas en memoria caché. Por ejemplo, un método puede devolver una tarea almacenada en caché para representar una operación completada en lugar de asignar una nueva tarea. Esto no era posible en versiones anteriores de .NET Framework, ya que cualquier consumidor de la tarea podía desecharla, lo que hacía que se volviera inutilizable.|  
|Sugerencia|Tenga en cuenta que los métodos Task puede que ya no inicien elementos ObjectDisposedException en casos en los que se deseche el objeto. Si una aplicación dependía de esta excepción para conocer que se desechó una tarea, debería actualizarse para comprobar de forma explícita el estado de la tarea mediante [Task.Status](https://msdn.microsoft.com/library/system.threading.tasks.task.status\(v=vs.110\).aspx).|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: Diferente control de excepciones para los métodos ObjectContext.CreateDatabase y DbProviderServices.CreateDatabase  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, si se produce un error de creación de base de datos, los métodos `CreateDatabase` tratarán de eliminar la base de datos vacía. Si la operación se realiza correctamente, se propagará el elemento `SQLException` original (en lugar del elemento `InvalidOperationException`, que ya se iniciaba siempre en .NET Framework 4.0).|  
|Sugerencia|Al detectar un elemento InvalidOperationException durante la ejecución de un método ObjectContext.CreateDatabase o DbProviderServices.CreateDatabase, ahora deberían detectarse también los elementos SQLException.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analizadores|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: Los métodos ObjectContext.Translate y ObjectContext.ExecuteStoreQuery ahora admiten el tipo enum  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.0, el parámetro genérico `T` de los métodos `ObjectContext.Translate` y `ObjectContext.ExecuteStoreQuery` no podía ser un tipo enum. Ahora se admite este escenario.|  
|Sugerencia|Si se llamaba a un elemento Translate o ExecuteStoreQuery en un tipo enum en .NET Framework 4.0, devolvía "0". Si este era el comportamiento deseado, las llamadas deberían reemplazarse por una constante 0 (o su tipo enum equivalente).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|Analizadores|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: El elemento Enumerable.Empty\<TResult> siempre devuelve una instancia almacenada en caché  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, `Enumerable.Empty` siempre devuelve una instancia interna `IEnumerable<T>` almacenada en caché.<br /><br /> Anteriormente, `Enumerable.Empty` almacenaba en caché un elemento `IEnumerable<T>` vacío en el momento de llamar a la API, lo que significa que, en ciertas condiciones en las que se llamaba al elemento `Enumerable.Empty` de forma rápida y simultánea, podían devolverse diferentes instancias del tipo para diferentes llamadas a la API.|  
|Sugerencia|Puesto que el comportamiento anterior no era determinista, es poco probable que el código dependa de él. No obstante, en el improbable caso de que se comparen enumerables vacíos y que se espere que a veces sean distintos, deberían crearse matrices vacías explícitas (`new T[0]`) en lugar de usar `Enumerable.Empty`.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|Analizadores|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: La propiedad HttpRequest.ContentEncoding prohíbe la codificación UTF7  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, la codificación UTF-7 está prohibida en los cuerpos de elementos HttpRequest. Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.|  
|Sugerencia|Lo ideal sería actualizar las aplicaciones para que no usen la codificación UTF-7 en elementos HttpRequest. También es posible restaurar el comportamiento heredado usando el atributo `aspnet:AllowUtf7RequestContentEncoding` del elemento [appSettings](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Web.HttpRequest.ContentEncoding%2A?displayProperty=fullName>|  
|Analizadores|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la y comercial  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, JavaScriptStringEncode aplica un carácter de escape al carácter de y comercial (&).|  
|Sugerencia|Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx) en el archivo de configuración.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener trunca las cadenas con caracteres nulos insertados  
  
|||  
|-|-|  
|Detalles|EventListener trunca las cadenas con caracteres nulos insertados. La clase EventSource no admite caracteres nulos. El cambio solo afecta a las aplicaciones que usan EventListener para leer datos de EventSource en proceso y que usan caracteres nulos como delimitadores.|  
|Sugerencia|Deberían actualizarse los datos de EventSource, si fuera posible, para que no usasen caracteres nulos insertados.|  
|Ámbito|Borde|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName>|  
|Analizadores|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD  
  
|||  
|-|-|  
|Detalles|Cuando crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo ObsoleteAttribute se exporta como ObsoleteAttribute y como Windows.Foundation.DeprecatedAttribute.|  
|Sugerencia|Volver a compilar el código fuente existente que use el atributo ObsoleteAttribute puede generar advertencias al usar dicho código desde C++/CX o JavaScript.<br /><br /> No se recomienda aplicar ObsoleteAttribute ni Windows.Foundation.DeprecatedAttribute al código en los ensamblados administrados; se podrían producir advertencias de compilación.|  
|Ámbito|Borde|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|Analizadores|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: La tarea ResolveAssemblyReference ahora advierte sobre dependencias con arquitectura incorrecta  
  
|||  
|-|-|  
|Detalles|La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación. Por ejemplo, se produce si una aplicación compilada con la opción anycpu incluye una referencia a x86. Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución (en este caso, si la aplicación se implementa como un proceso x64).|  
|Sugerencia|Existen dos áreas de impacto:<br /><br /> Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild. Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.<br /><br /> Si las advertencias se tratan como errores, la aplicación no se compilará.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|Analizadores|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).|  
|Sugerencia|Si el límite de 100 para la fase de reversión es demasiado bajo, es posible establecerlo de forma explícita con la propiedad UndoLimit de cuadros de texto.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analizadores|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: Las excepciones durante el procesamiento inadvertido en System.Threading.Tasks.Task ya no se propagan por el subproceso de finalizador  
  
|||  
|-|-|  
|Detalles|Dado que la clase System.Threading.Tasks.Task representa una operación asincrónica, detecta todas las excepciones no graves que se producen durante el procesamiento asincrónico. En .NET Framework 4.5, si no se detecta una excepción y el código nunca espera a que se complete la tarea, la excepción ya no se propagará por el subproceso de finalizador y bloqueará el proceso durante la recolección de elementos no utilizados. Este cambio mejora la confiabilidad de las aplicaciones que usan la clase Task para realizar un procesamiento asincrónico inadvertido.|  
|Sugerencia|Si una aplicación depende de la propagación de excepciones asincrónicas inadvertidas al subproceso de finalizador, es posible restaurar el comportamiento anterior proporcionando un controlador adecuado para el evento [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) o estableciendo un [elemento de configuración de runtime](https://msdn.microsoft.com/library/jj160346%28v=vs.110%29.aspx).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|Analizadores|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: La propiedad IAsyncResult.CompletedSynchronously debe ser correcta para que se complete la tarea resultante  
  
|||  
|-|-|  
|Detalles|Al llamar a TaskFactory.FromAsync, la implementación de la propiedad IAsyncResult.CompletedSynchronously debe ser correcta para que se complete la tarea resultante. Es decir, la propiedad debe devolver true solo si la implementación se completó de manera sincrónica. Anteriormente, esta propiedad no se comprobaba.|  
|Sugerencia|Si las implementaciones de IAsyncResult devuelven el valor correcto true para la propiedad CompletedSynchronusly solo cuando una tarea se completa de manera sincrónica, no se observará ninguna interrupción. Los usuarios deberían revisar las implementaciones de IAsyncResult que posean (en caso de poseer alguna) para asegurarse de que evalúan correctamente si una tarea se completó de forma sincrónica o no.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName>|  
|Analizadores|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: El nombre de archivo de registro creado por el método ObjectContext.CreateDatabase cambió para coincidir con las especificaciones de SQL Server  
  
|||  
|-|-|  
|Detalles|Cuando se llama al método CreateDatabase, ya sea directamente o mediante Code First con el proveedor SqlClient y un valor AttachDBFilename en la cadena de conexión, se crea un archivo de registro denominado nombreDeArchivo_log.ldf en lugar de nombreDeArchivo.ldf (donde nombreDeArchivo es el nombre del archivo especificado mediante el valor AttachDBFilename). Este cambio mejora la depuración al proporcionar un archivo de registro cuyo nombre se ajusta a las especificaciones de SQL Server.|  
|Sugerencia|Si el nombre de archivo de registro es importante para una aplicación, la aplicación debería actualizarse para que espere el formato de nombre de archivo estándar _log.ldf.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analizadores|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: El evento Page.LoadComplete ya no hace que el control System.Web.UI.WebControls.EntityDataSource invoque un enlace de datos  
  
|||  
|-|-|  
|Detalles|El evento `Page.LoadComplete` ya no hace que el control System.Web.UI.WebControls.EntityDataSource invoque un enlace de datos cuando se producen cambios al crear, actualizar o eliminar parámetros. Este cambio elimina un recorrido extraño a la base de datos, impide que se restablezcan los valores de los controles y produce un comportamiento coherente con otros controles de datos, como SqlDataSource y ObjectDataSource. Este cambio produce un comportamiento diferente en el caso improbable de que las aplicaciones invoquen el enlace de datos en el evento `Page.LoadComplete`.|  
|Sugerencia|Si se necesita un enlace de datos, invóquelo manualmente en un evento anterior en la devolución.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode ya no descodifica secuencias de entrada no válidas  
  
|||  
|-|-|  
|Detalles|De forma predeterminada, los métodos de descodificación ya no descodifican secuencias de entrada no válidas en una cadena UTF-16 no válida. En su lugar, devuelven la entrada original.|  
|Sugerencia|El cambio en la salida del descodificador solo es importante si se almacenan datos binarios en lugar de datos UTF-16 en cadenas. Para controlar este comportamiento de manera explícita, establezca el atributo `aspnet:AllowRelaxedUnicodeDecoding` del elemento [appSettings](https://msdn.microsoft.com/library/ms228154\(v=vs.110\).aspx) en true para activar el comportamiento heredado o en false para activar el comportamiento actual.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|Analizadores|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: Puede producirse un error en las aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA-256 en Windows 2003  
  
|||  
|-|-|  
|Detalles|El archivo ejecutable está firmado con SHA-256. Antes se firmaba con SHA1, independientemente de si el certificado de firma de código era SHA-1 o SHA-256. Esto se aplica a lo siguiente:<br /><br /> Todas las aplicaciones compiladas con Visual Studio 2012 o versiones posteriores.<br /><br /> Aplicaciones compiladas con Visual Studio 2010 o versiones anteriores en sistemas con .NET Framework 4.5.<br /><br /> Además, si está presente .NET Framework 4.5 o versiones posteriores, el manifiesto de ClickOnce también está firmado con SHA-256 para certificados SHA-256, independientemente de la versión de .NET Framework con la que se compiló.|  
|Sugerencia|El cambio en la firma del ejecutable ClickOnce solo afecta a los sistemas Windows Server 2003; necesitan que KB 938397 esté instalado.<br /><br /> El cambio al firmar el manifiesto con SHA-256, incluso cuando una aplicación tiene como destino .NET Framework 4.0 o versiones anteriores, introduce una dependencia de tiempo de ejecución en .NET Framework 4.5 o versiones posteriores.|  
|Ámbito|Borde|  
|Versión|4.5-4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision y DbParameter.Scale son ahora miembros virtuales públicos  
  
|||  
|-|-|  
|Detalles|DbParameter.Precision y DbParameter.Scale se implementan como propiedades virtuales públicas. Reemplazan a las correspondientes implementaciones de interfaz explícitas DbParameter.IDbDataParameter.Precision y DbParameter.IDbDataParameter.Scale.|  
|Sugerencia|Al volver a compilar un proveedor de base de datos de ADO.NET, estas diferencias necesitarán que se aplique la palabra clave "override" a las propiedades Scale y Precision. Solo es necesario a la hora de volver a compilar los componentes; los binarios existentes continuarán funcionando.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|Analizadores|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData ahora recupera los datos como UTF-8  
  
|||  
|-|-|  
|Detalles|Para aplicaciones que tienen como destino .NET Framework 4 o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, DataObject.GetData recupera datos con formato HTML como una cadena ASCII. Como resultado, los caracteres que no son ASCII (cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios.<br /><br /> Para aplicaciones que tienen como destino .NET Framework 4.5 o posterior y que se ejecutan en .NET Framework 4.5.2, `DataObject.GetData` recupera datos con formato HTML como UTF-8, que representa correctamente caracteres mayores que 0x7F.|  
|Sugerencia|Si implementó una solución alternativa para el problema de codificación mediante cadenas con formato HTML (por ejemplo, si codifica de manera explícita la cadena HTML recuperada del Portapapeles transfiriéndola al método UTF8Encoding.GetString) y cambia el destino de la aplicación de la versión 4 a la versión 4.5, debería eliminar dicha solución alternativa.<br /><br /> Si por cualquier motivo se necesitara el comportamiento anterior, puede establecerse .NET Framework 4.0 como destino de la aplicación para conseguir dicho comportamiento.|  
|Ámbito|Borde|  
|Versión|4.5.2|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|Analizadores|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: La propiedad TargetFrameworkName para el dominio de aplicación predeterminado ya no tiene un valor nulo como valor predeterminado si no se establece  
  
|||  
|-|-|  
|Detalles|TargetFrameworkName anteriormente tenía un valor nulo en el dominio de aplicación predeterminado a menos que se estableciera de forma explícita. A partir de la versión 4.6, la propiedad TargetFrameworkName del dominio de aplicación predeterminado tendrá un valor predeterminado derivado del elemento TargetFrameworkAttribute (si hubiera alguno presente). Los dominios de aplicación no predeterminados continuarán heredando la propiedad TargetFrameworkName del dominio de aplicación predeterminado (que no tendrá un valor nulo como valor predeterminado en la versión 4.6) a menos que se invalide de forma explícita.|  
|Sugerencia|El código debería actualizarse para no depender de que `AppDomainSetup.TargetFrameworkName` establezca un valor nulo como valor predeterminado. Si es necesario que esta propiedad continúe evaluándose como un valor nulo, puede establecerse en dicho valor de forma explícita.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|Analizadores|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: El elemento X509Certificate2.ToString(bool) ahora no se inicia cuando .NET Framework no pueda controlar el certificado  
  
|||  
|-|-|  
|Detalles|Anteriormente, este método se iniciaba si se pasaba "true" para el parámetro detallado y había certificados instalados no admitidos por .NET Framework. Ahora, el método se realizará correctamente y devolverá una cadena válida que omita las partes inaccesibles del certificado.|  
|Sugerencia|Cualquier código que dependa de X509Certificate2.ToString(bool) debería actualizarse para esperar que la cadena devuelta excluya algunos datos del certificado (como la clave pública, la clave privada y las extensiones) en ciertos casos en los que anteriormente se habría iniciado la API.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: Los objetos Reflection ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso  
  
|||  
|-|-|  
|Detalles|Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Afecta a los siguientes tipos:<br /><br /> Ensamblado<br /><br /> MemberInfo (y sus tipos derivados, incluidos FieldInfo, MethodInfo, Type y TypeInfo)<br /><br /> MethodBody<br /><br /> Módulo<br /><br /> ParameterInfo<br /><br /> Las llamadas a `IMarshal` para el objeto devuelven `E_NOINTERFACE`.|  
|Sugerencia|Actualice el código de serialización para que funcione con objetos distintos a Reflection.|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition DateTimes devuelve una cadena ligeramente diferente  
  
|||  
|-|-|  
|Detalles|Se han actualizado las representaciones de cadena de los elementos ContentDisposition a partir de la versión 4.6 para que manifiesten siempre el componente de hora de un elemento DateTime con dos dígitos. La finalidad es cumplir con [RFC822](http://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](http://www.ietf.org/rfc/rfc2822.txt). De este modo, `ContentDisposition.ToString` devuelve una cadena ligeramente diferente en escenarios de la versión 4.6 en los que uno de los elementos de hora de la disposición era anterior a las 10:00. Tenga en cuenta que los elementos ContentDisposition a veces se serializan convirtiéndolos en cadenas, por lo que debería revisarse cualquier operación ContentDisposition ToString, serialización o llamada a GetHashCode.|  
|Sugerencia|No espere que las representaciones de cadena de elementos ContentDisposition de otras versiones de .NET Framework se comparen correctamente entre sí. Vuelva a convertir las cadenas a elementos ContentDisposition, si fuera posible, antes de realizar una comparación.|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|Analizadores|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: El método WorkflowDesigner.Load no elimina una propiedad de símbolo  
  
|||  
|-|-|  
|Detalles|Al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo y cargar un flujo de trabajo de la versión 3.5 rehospedado con el método WorkflowDesigner.Load(), se inicia un elemento XamlDuplicateMemberException mientras se guarda el flujo de trabajo.|  
|Sugerencia|Este error solo se manifiesta al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo, por lo que una posible solución alternativa es establecer `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` a la versión 4.0 de .NET Framework.<br /><br /> También es posible evitar este problema usando el método [WorkflowContext.Load(string)](https://msdn.microsoft.com/library/ee425926\(v=vs.110\).aspx) en lugar de [WorkflowDesigner.Load()](https://msdn.microsoft.com/library/ee403482\(v=vs.110\).aspx) para cargar el flujo de trabajo.|  
|Ámbito|Major|  
|Versión|4.5-4.5.2|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|Analizadores|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: Se produce un error de SqlConnection.Open en Windows 7 con presencia de un BSP o LSP de Winsock distinto de IFS  
  
|||  
|-|-|  
|Detalles|Se produce un error con los elementos SqlConneciton.Open y OpenAsync en .NET Framework 4.5 si se ejecutan en una máquina con Windows 7 con presencia de un BSP o LSP de Winsock distinto de IFS en el PC.<br /><br /> Para determinar si hay un BSP o LSP distinto de IFS instalado, use el comando `netsh WinSock Show Catalog` y examine cada elemento `Winsock Catalog Provider Entry` devuelto. Si el valor Service Flags tiene establecido el bit `0x20000`, el proveedor usa controladores IFS y funcionará correctamente. Si el bit `0x20000` está claro (no establecido), se trata de un BSP o LSP distinto de IFS.|  
|Sugerencia|Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework. También puede evitarse eliminando cualquier LSP de Winsock distinto de IFS que haya instalado.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5.2|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|Analizadores|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: Cambio de comportamiento del evento ICommand.CanExecuteChanged en .NET Framework 4.5  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, los elementos CanExecuteChangedEvent se omitían a menos que el remitente del evento fuese el mismo objeto que lo generó. Este error se corrigió en actualizaciones de servicio de .NET Framework 4.5.|  
|Sugerencia|Este error se corrigió en actualizaciones de servicio de .NET Framework 4.5, por lo que puede evitarse asegurándose de mantener actualizado .NET Framework o actualizando a .NET Framework 4.5.1. También puede modificarse el código de aplicación mediante ICommand para asegurarse de que el remitente sea el mismo que el objeto que genera el evento al generar un comando CanExecuteChanged.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|Analizadores|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: Algunas API de .NET Framework generan primeras excepciones (controladas) EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, un pequeño número de métodos de Framework .NET comenzaron a iniciar primeras excepciones EntryPointNotFoundException. Estas primeras excepciones se controlaban dentro de .NET Framework, pero podían interrumpir la automatización de pruebas que no las esperasen. Estas mismas API interrumpen algunos escenarios de ApiVerifier con el elemento HighVersionLie habilitado.|  
|Sugerencia|Este error puede evitarse actualizando a .NET Framework 4.5.1. También es posible actualizar la automatización de pruebas para que no se interrumpa con las primeras excepciones EntryPointNotFoundException.|  
|Ámbito|Borde|  
|Versión|4.5-4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|Analizadores|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: Desplazar una instancia TreeView de WPF o ListBox agrupado en un elemento VirtualizingStackPanel puede hacer que el programa no responda  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, desplazar una instancia TreeView de WPF en un panel StackPanel virtualizado puede hacer que el programa no responda si hay márgenes en la ventanilla (entre los elementos de TreeView o en algún elemento ItemsPresenter). Además, en algunos casos, los elementos de diferentes tamaños de la vista pueden originar inestabilidad aun cuando no haya márgenes.|  
|Sugerencia|Este error puede evitarse actualizando a .NET Framework 4.5.1. También es posible eliminar los márgenes de las colecciones de la vista (como instancias TreeView) dentro de paneles StackPanel si todos los elementos contenidos son del mismo tamaño.|  
|Ámbito|Major|  
|Versión|4.5-4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.VirtualizingPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom devuelve un resultado incorrecto para variables genéricas con restricciones  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, Type.IsAssignableFrom devolverá por error `false` en todos los casos para algunos tipos genéricos con restricciones.|  
|Sugerencia|Este problema se corrigió en una actualización de servicio. Para corregir este problema, actualice .NET Framework 4.5 o actualice a la versión 4.5.1 o posterior de .NET Framework. También puede evitar usar IsAssignableFrom con tipos genéricos que tengan restricciones sobre parámetros genéricos. Se pueden usar API de reflexión a modo de solución alternativa.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|Analizadores|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: EntityFramework 6.0 se carga muy lentamente en las aplicaciones iniciadas desde Visual Studio  
  
|||  
|-|-|  
|Detalles|Iniciar una aplicación desde Visual Studio 2013 que usa EntityFramework 6.0 puede resultar muy lento.|  
|Sugerencia|Este problema se corrigió en EntityFramework 6.0.2. Actualice EntityFramework para evitar este problema de rendimiento.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: Cambio de interlineado de los cuadros de texto multilínea de ASP.NET al usar AntiXSSEncoder  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.0, se introdujeron líneas adicionales entre las líneas de un cuadro de texto multilínea en postback si se usaba el elemento `AntiXSSEncoder`. En .NET Framework 4.5 no se incluyen estos saltos de línea adicionales, pero únicamente si la aplicación web tiene como destino .NET 4.5.|  
|Sugerencia|Tenga en cuenta que las aplicaciones web de la versión 4.0 cuyo destino se haya cambiado a .NET 4.5 pueden tener cuadros de texto multilínea mejorados para dejar de introducir saltos de línea adicionales. Si este no es el comportamiento deseado, es posible recuperar el al ejecutar la aplicación en .NET Framework 4.5 estableciendo como destino .NET Framework 4.0.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|Analizadores|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue\<T >. TryPeek puede devolver un valor nulo erróneo mediante su parámetro out  
  
|||  
|-|-|  
|Detalles|En algunos escenarios con múltiples subprocesos, `ConcurentQueue<T>.TryPeek` puede devolver true, pero rellenar el parámetro out con un valor nulo (en lugar del valor correcto observado).|  
|Sugerencia|Este problema se corrigió en .NET Framework 4.5.1. Actualizar a esta versión de .NET Framework solucionará el problema.|  
|Ámbito|Major|  
|Versión|4.5-4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|Analizadores|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: Es posible reordenar varios elementos en una única celda TableLayoutPanel  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, si hay varios elementos colocados en la misma celda TableLayoutPanel, pueden aparecer en un orden diferente al de .NET Framework 4.0.|  
|Sugerencia|Este comportamiento se revirtió en una actualización de servicio para .NET Framework 4.5. Para corregir este problema, actualice .NET Framework 4.5 o actualice a la versión 4.5.1 o posterior de .NET Framework. También puede evitarse el caso ambiguo de colocar varios elementos en la misma celda TableLayourPanel.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analizadores|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: La variable de iterador Foreach ahora tiene como ámbito la iteración, por lo que la semántica de captura de clausura es diferente (en C#5)  
  
|||  
|-|-|  
|Detalles|A partir de C#5 (Visual Studio 2012), las variables de iterador Foreach tienen como ámbito la iteración. Esto puede provocar interrupciones si el código dependía anteriormente de que no se incluyeran variables en la clausura de la variable Foreach. El síntoma de este cambio será que una variable de iterador pasada a un delegado se tratará como el valor que tuviera en el momento de creación del delegado, en lugar de como el valor que tenía en el momento de invocar al delegado.|  
|Sugerencia|Lo ideal sería actualizar el código para que espere el nuevo comportamiento del compilador. Si es necesario usar la semántica anterior, es posible reemplazar la variable de iterador por una variable independiente colocada de forma explícita fuera del ámbito del bucle.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Redestinación|  
|Analizadores|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter no representa el elemento \`<br/\> de forma correcta  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.6, al llamar a `HtmlTextWriter.RenderBeginTag()` y `HtmlTextWriter.RenderEndTag()` con un elemento `<BR />` solo insertará correctamente un `<BR />` (en lugar de dos).|  
|Sugerencia|Si alguna aplicación dependía de la etiqueta `<BR />` adicional, debería llamarse a `HtmlTextWriter.RenderBeginTag()` una segunda vez. Tenga en cuenta que este cambio de comportamiento solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6, por lo que otra opción es seleccionar como destino una versión anterior de .NET Framework para conseguir el comportamiento anterior.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|Analizadores|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: Llamar a Items.Refresh en un elemento ListBox o ListView, o una cuadrícula de datos de WPF con elementos seleccionados puede hacer que aparezcan elementos duplicados en el elemento  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, llamar a ListBox.Items.Refresh desde el código con elementos seleccionados en un elemento ListBox puede hacer que los elementos seleccionados se dupliquen en la lista. Se produce un problema similar con ListView y las cuadrículas de datos. Este problema se corrigió en .NET Framework 4.6.|  
|Sugerencia|Una solución alternativa para este problema consiste en, mediante programación, anular la selección de elementos antes de llamar a Refresh y volver a seleccionarlos después de que la llamada se complete. Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|Analizadores|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: Los elementos EventListener de ETW no capturan eventos de proveedores con palabras clave explícitas (como el proveedor de la TPL)  
  
|||  
|-|-|  
|Detalles|Los elementos EventListener de ETW con una máscara de palabra clave en blanco no capturarán correctamente los eventos de proveedores con palabras clave explícitas. En .NET Framework 4.5, el proveedor de la TPL comenzó a suministrar palabras clave explícitas y dio pie a este problema. En .NET Framework 4.6, se actualizaron los elementos EventListener para evitar este problema.|  
|Sugerencia|A modo de solución alternativa para este problema, sustituya las llamadas a EnableEvents(eventSource, level) por llamadas a la sobrecarga EnableEvents que especifique de forma explícita que la máscara "any keywords" debe usar `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`.<br /><br /> Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.|  
|Ámbito|Borde|  
|Versión|4.5-4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|Analizadores|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: Puede producirse un error MSB4062 al compilar un archivo .edmx de Entity Framework con Visual Studio 2013 si se usan las tareas EntityDeploySplit o EntityClean  
  
|||  
|-|-|  
|Detalles|Las herramientas de MSBuild 12.0 (incluidas en Visual Studio 2013) cambiaron las ubicaciones de los archivos de MSBuild, lo que invalida los archivos de destinos antiguos de Entity Framework. El resultado es un error de las tareas `EntityDeploySplit` y `EntityClean` debido a que no pueden buscar `Microsoft.Data.Entity.Build.Tasks.dll`. Tenga en cuenta que esta es una interrupción producida como consecuencia de un cambio en un conjunto de herramientas (MSBuild/Visual Studio), no en .NET Framework. Solo se producirá al actualizar las herramientas de desarrollo, no al actualizar únicamente .NET Framework.|  
|Sugerencia|Los archivos de destinos de Entity Framework se modificaron para funcionar con el nuevo diseño de MSBuild a partir de .NET Framework 4.6. Este problema se soluciona actualizando a esta versión de .NET Framework. También es posible usar [esta](http://stackoverflow.com/a/24249247/131944) solución alternativa para aplicar la revisión directamente a los archivos de destinos.|  
|Ámbito|Major|  
|Versión|4.5.1-4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: La validación del esquema XSD ahora detecta correctamente las infracciones de restricciones únicas si se usan claves compuestas y una de las claves está vacía  
  
|||  
|-|-|  
|Detalles|Las versiones de .NET Framework anteriores a la 4.6 presentaban un error que hacía que la validación de XSD no detectara restricciones únicas en claves compuestas si alguna de las claves estaba vacía. Este problema se corrigió en .NET Framework 4.6. De este modo, se conseguirá una mayor corrección en la validación, pero también podría hacer que cierto XML no valide lo que antes sí validaría.|  
|Sugerencia|Si se necesita una validación de .NET Framework 4.0 (menos estricta), puede establecerse la versión 4.5 (o anterior) de .NET Framework como destino de la validación. No obstante, al cambiar el destino a .NET Framework 4.6, debería revisarse el código para asegurarse de que no se espere la validación de claves compuestas duplicadas (como se indica en la descripción de este problema).|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: Las llamadas a Attribute.GetCustomAttributes en una propiedad de indizador ya no inician AmbiguousMatchException si es posible resolver la ambigüedad con el tipo de índice  
  
|||  
|-|-|  
|Detalles|Antes de .NET Framework 4.6, llamar a `GetCustomAttribute(s)` en una propiedad de indizador que difiriera de otra propiedad solo en el tipo de índice daba lugar a una instancia de `AmbiguousMatchException`. A partir de .NET Framework 4.6, los atributos de la propiedad se devolverán correctamente.|  
|Sugerencia|Tenga en cuenta que GetCustomAttribute(s) ahora funcionará con mayor frecuencia. Si anteriormente alguna aplicación se basaba en el elemento `AmbiguousMatchException`, ahora se debería usar una reflexión para buscar varios indizadores de forma explícita en su lugar.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: Incapacidad intermitente de desplazarse hasta el último elemento de instancias ItemsControl (como ListBox y una cuadrícula de datos) al usar elementos DataTemplate personalizados  
  
|||  
|-|-|  
|Detalles|En algunos casos, un error de .NET Framework 4.5 impide desplazarse hasta el último elemento de instancias ItemsControl (como ListBox, ComboBox, una cuadrícula de datos, etc.) al usar elementos DataTemplate personalizados. Si se trata de efectuar el desplazamiento una segunda vez (después de haber vuelto arriba), sí funciona.|  
|Sugerencia|Este problema se resolvió en .NET Framework 4.5.2, por lo que otra posible solución es actualizar a esta versión (u otra posterior) de .NET Framework. Los usuarios también pueden arrastrar las barras de desplazamiento hasta los últimos elementos de estas colecciones, pero puede ser posible que tengan que hacerlo dos veces para conseguirlo.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5.2|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent devuelven diferentes valores a partir de .NET Framework 4.5  
  
|||  
|-|-|  
|Detalles|Se efectuaron mejoras en los elementos GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent en .NET Framework 4.5 para solucionar problemas por los que los rectángulos eran demasiado pequeños para los glifos que contenían en ciertas ocasiones en .NET Framework 4.0. Como resultado de ello, algunos rectángulos de selección son más grandes a partir de .NET Framework 4.5, por lo que hay ligeras diferencias en el diseño de la IU.|  
|Sugerencia|Tenga en cuenta que los rectángulos de selección de algunos glifos ahora son de mayor tamaño. Por lo general, estos cambios mejorarán la presentación y las pruebas de acierto de los rectángulos, pero si se quiere revertir al comportamiento anterior (previo a la versión 4.5 de .NET Framework), puede añadirse la siguiente entrada al archivo app.config:<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|Analizadores|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: Llamar a DataGrid.CommitEdit desde un controlador CellEditEnding elimina el foco  
  
|||  
|-|-|  
|Detalles|Llamar a DataGrid.CommitEdit desde uno de los controladores de eventos CellEditEnding de la cuadrícula de datos hace perder el foco de la cuadrícula de datos.|  
|Sugerencia|Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework. También puede evitarse volviendo a seleccionar la cuadrícula de datos de forma explícita después de llamar a CommitEdit.|  
|Ámbito|Borde|  
|Versión|4.5-4.5.2|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC ahora aplica caracteres de escape a los espacios de las cadenas pasados a través de parámetros de ruta  
  
|||  
|-|-|  
|Detalles|Para cumplir con RFC 2396, ahora se aplican caracteres de escape a los espacios de las rutas de acceso al rellenar parámetros de acción desde una ruta. Por tanto, mientras que `/controller/action/some data` antes coincidía con la ruta `/controller/action/{data}` y proporcionaba `some data` como parámetro de datos, ahora proporciona `some%20data`.|  
|Sugerencia|Debería actualizarse el código para no eliminar las secuencias de escape de los parámetros de las cadenas desde una ruta. Si se necesita el identificador URI original, puede accederse a él con la API Request.RequestUri.OriginalString.|  
|Ámbito|Secundaria|  
|Versión|4.5.2|  
|Tipo|Tiempo de ejecución|  
|API afectadas|[System.Web.Http.RouteAttribute](https://msdn.microsoft.com/library/system.web.http.routeattribute(v=vs.118).aspx)|  
|Analizadores|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET ya no admite espacios de nombres parciales para las API System.Windows  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales. Por ejemplo, se producirá un error al hacer referencia a `Windows.Forms.DialogResult`. En su lugar, el código debe hacer referencia al nombre completo (`System.Windows.Forms.DialogResult`) o importar el espacio de nombres específico y simplemente hacer referencia a `DialogResult`.|  
|Sugerencia|Debería actualizarse el código para hacer referencia a las API `System.Windows` con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.|  
|Ámbito|Secundaria|  
|Versión|4.5.2|  
|Tipo|Redestinación|  
|Analizadores|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: No se admite el enlace de datos bidireccional a una propiedad con un establecedor no público  
  
|||  
|-|-|  
|Detalles|Nunca se ha admitido el escenario de tratar de enlazar datos a una propiedad sin establecedor público. A partir de .NET Framework 4.5.1, este escenario, iniciará una instancia InvalidOperationException. Tenga en cuenta que esta nueva excepción solo se iniciará para aquellas aplicaciones que tengan .NET Framework 4.5.1 como destino específico. Si una aplicación tiene como destino .NET Framework 4.5, se permitirá la llamada. Si la aplicación no tiene como destino ninguna versión concreta de .NET Framework, el enlace se tratará como unidireccional.|  
|Sugerencia|Debería actualizarse la aplicación para utilizar un enlace bidireccional, o bien para exponer públicamente el establecedor de la propiedad. También es posible establecer .NET Framework 4.5 como destino para que la aplicación presente el comportamiento anterior.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|Analizadores|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Las sobrecargas Marshal.SizeOf y Marshal.PtrToStructure interrumpen el código dinámico  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5.1, el enlace dinámico a los métodos `Marshal.SizeOf` o `Marshal.PtrToStructure` (por ejemplo, a través de Windows PowerShell, IronPython o la palabra clave dynamic de C#) puede dar lugar a `MethodInvocationExceptions`, ya que se agregaron nuevas sobrecargas de estos métodos que pueden resultar ambiguas para los motores de secuencia de comandos.|  
|Sugerencia|Actualice los scripts para que indiquen claramente qué sobrecarga debería usarse. Normalmente, puede hacerse convirtiendo de forma explícita los parámetros de tipo del método como `System.Type`. Visite [este vínculo](https://support.microsoft.com/kb/2909958/) para consultar información más detallada y ejemplos de soluciones alternativas para este problema.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: Se llama repetidas veces a PreviewLostKeyboardFocus si su controlador muestra un cuadro de mensaje de Windows Forms  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, si se llama a `System.Windows.Forms.MessageBox.Show` desde un controlador de `UIElement.PreviewLostKeyboardFocus`, se volverá a activar el controlador al cerrar el cuadro de mensaje, lo que podría generar un bucle infinito de cuadros de mensaje.|  
|Sugerencia|Hay dos opciones para solucionar este problema:<br /><br /> Se puede evitar llamando a `System.Windows.MessageBox.Show` en lugar de a `System.Windows.Forms.MessageBox.Show`.<br /><br /> Se puede evitar mostrando el cuadro de mensaje desde un controlador de eventos `LostKeyboardFocus` (en contraposición a un controlador de eventos `PreviewLostKeyboardFocus`).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|Analizadores|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: Los elementos ConcurrentDictionary serializados en .NET Framework 4.5 con NetDataContractSerializer no se pueden deserializar en .NET Framework 4.5.1 ni 4.5.2  
  
|||  
|-|-|  
|Detalles|Como consecuencia de cambios internos efectuados en el tipo, los objetos `System.Collections.Concurrent.ConcurrentDictionary` serializados con .NET Framework 4.5 que usen el elemento `NetDataContractSerializer` no se pueden deserializar en .NET Framework 4.5.1 ni en NET Framework 4.5.2.<br /><br /> Tenga en cuenta que sí es posible realizar el proceso inverso (serializar con .NET Framework 4.5.x y deserializar con .NET Framework 4.5). Del mismo modo, .NET Framework 4.6 permite la serialización entre todas las versiones 4.x.<br /><br /> La serialización y la deserialización con una única versión de .NET Framework no se ven afectadas.|  
|Sugerencia|Si es necesario serializar y deserializar un elemento ConcurrentDictionary entre las versiones de .NET Framework 4.5 y 4.5.1 o 4.5.2, debería utilizarse un serializador distinto, como DataContractSerializer o BinaryFormatter, en lugar de NetDataContractSerializer.<br /><br /> Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.|  
|Ámbito|Secundaria|  
|Versión|4.5.1-4.6|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: El calendario persa ahora usa el algoritmo Hijri solar  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.6, la clase PersianCalendar usa el algoritmo Hijri solar. Convertir fechas entre PersianCalendar y otros calendarios puede producir un resultado ligeramente diferente a partir de .NET Framework 4.6 para fechas anteriores a 1800 o posteriores a 2023 (del calendario gregoriano).<br /><br /> Además, `PersianCalendar.MinSupportedDateTime` ahora es `March 22, 0622 instead of March 21, 0622`.|  
|Sugerencia|Tenga en cuenta que algunas fechas tempranas o tardías pueden ser ligeramente diferentes al utilizar PersianCalendar en .NET Framework 4.6. Además, al serializar fechas entre procesos que puedan ejecutarse en diferentes versiones de .NET Framework, no las guarde como cadenas de fecha de PersianCalendar (ya que estos valores pueden ser diferentes).|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|Analizadores|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: La llamada a CreateDefaultAuthorizationContext con un argumento nulo ha cambiado  
  
|||  
|-|-|  
|Detalles|La implementación del elemento AuthorizationContext devuelto por una llamada a `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` con un argumento authorizationPolicies nulo cambió en .NET Framework 4.6.|  
|Sugerencia|En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento. En estos casos, es posible restaurar el comportamiento anterior de dos maneras:<br /><br /> Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6. Para los servicios hospedados en IIS, use el elemento \<httpRuntime targetFramework="x.x" /> para establecer como destino una versión anterior de .NET Framework.<br /><br /> Agregue la siguiente línea a la sección `<appSettings>` del archivo app.config: `<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`.|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|Analizadores|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: El elemento TreeViewItem de WPF debe utilizarse dentro de una instancia TreeView  
  
|||  
|-|-|  
|Detalles|Se introdujo un cambio en la versión 4.5 que restringe la utilización de elementos TreeViewItem fuera de una instancia TreeView. Se manifiesta en las siguientes condiciones:<br /><br /> Cuando el primario del objeto visual de TreeViewItem no sea un panel (un elemento TreeViewItem generado para una instancia TreeView tendrá un panel como primario).<br /><br /> Cuando el elemento TreeViewItem sea un descendiente de una instancia VirtualizingStackPanel que actúe como "host de elementos" para un control de lista (ListBox, cuadrícula de datos, ListView, etc.). No es necesario que la virtualización esté activada.<br /><br /> Cuando la instancia VirtualizingStackPanel esté desplazando elementos (`ScrollUnit="Item"`).<br /><br /> Alguien llama a `VirtualizingStackPanel.MakeVisible(v)` para desplazar un elemento `v` a la vista. Puede hacerse de forma explícita, o bien implícita de diferentes formas; tal vez la más habitual sea simplemente hacer clic en `v` para asignarle el foco del teclado.<br /><br /> La cadena objeto visual-primario de `v` a VirtualizingStackPanel pasa a través de TreeViewItem.<br /><br /> En otras palabras, este fenómeno se observa cuando al utilizar un elemento TreeViewItem fuera de una instancia TreeView, el usuario hace clic en un descendiente del elemento TreeViewItem para desplazarlo a la vista. Si el elemento TreeViewItem no tiene ningún descendiente activable, nunca observará este problema. Un ejemplo de situación en la que se produce este problema es cuando el elemento TreeViewItem es la raíz de una instancia DataTemplate.  Cuando se produce este problema, se genera una instancia InvalidCastException dentro del marco de WPF.|  
|Sugerencia|Se lanzará una revisión para esta solucionar esta situación.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims considera todos los argumentos claimType  
  
|||  
|-|-|  
|Detalles|En aplicaciones que tengan como destino .NET Framework 4.6.1, si un conjunto de notificaciones X509 se inicia desde un certificado que tenga varias entradas DNS en su campo SAN, el método FindClaims tratará de hacer coincidir el argumento claimType con todas las entradas DNS.<br /><br /> Para aquellas aplicaciones que tengan como destino versiones anteriores de .NET Framework, el método FindClaims trata de hacer coincidir el argumento claimType solo con la última entrada DNS.|  
|Sugerencia|Este cambio solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6.1. Este cambio puede deshabilitarse (o habilitarse si se establece como destino una versión anterior a la 4.6.1) con el modificador de compatibilidad [DisableMultipleDNSEntries](https://msdn.microsoft.com/library/mt620030%28v=vs.110%29.aspx).|  
|Ámbito|Secundaria|  
|Versión|4.6.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|Analizadores|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Ya no se inicia Application.FilterMessage para implementaciones reentrantes de IMessageFilter.PreFilterMessage  
  
|||  
|-|-|  
|Detalles|Antes de .NET Framework 4.6.1, llamar a Application.FilterMessage con un elemento IMessageFilter.PreFilterMessage que llamaba a AddMessageFilter o RemoveMessageFilter (a la vez que también llamaba a Application.DoEvents), provocaba una instancia IndexOutOfRangeException.<br /><br /> A partir de las aplicaciones que tengan como destino .NET Framework 4.6.1, esta excepción ya no se inicia y es posible usar los filtros reentrantes como se indica anteriormente.|  
|Sugerencia|Tenga en cuenta que ya no se iniciará Application.FilterMessage para el comportamiento reentrante de IMessageFilter.PreFilterMessage descrito anteriormente. Esto solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6.1.<br /><br /> Es posible desactivar este cambio en las aplicaciones que tengan como destino .NET Framework 4.6.1 (o activarlo en las aplicaciones que tengan como destino versiones anteriores de .NET Framework) utilizando el modificador de compatibilidad [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/library/mt620032%28v=vs.110%29.aspx).|  
|Ámbito|Borde|  
|Versión|4.6.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|Analizadores|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture no se conserva entre operaciones del distribuidor de WPF  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.6, los cambios efectuados en CurrentCulture o CurrentUICulture dentro de un [distribuidor](https://msdn.microsoft.com/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) se perderán al final de la operación de dicho distribuidor. De igual modo, los cambios efectuados en CurrentCulture o CurrentUICulture fuera de una operación de distribuidor pueden no reflejarse cuando se ejecute dicha operación.<br /><br /> En términos prácticos, significa que puede que los cambios efectuados en CurrentCulture y CurrentUICulture no se transmitan entre devoluciones de llamadas de la IU de WPF y otro código de alguna aplicación WPF.<br /><br /> El motivo es un cambio en [ExecutionContext](https://msdn.microsoft.com/library/system.threading.executioncontext%28v=vs.110%29.aspx) que hace que CurrentCulture y CurrentUICulture se almacenen en el contexto de ejecución a partir de las aplicaciones que tengan como destino .NET Framework 4.6. Las operaciones de distribuidor de WPF almacenan el contexto de ejecución usado para iniciar la operación y restaurar el contexto anterior cuando la operación se complete. Dado que CurrentCulture y CurrentUICulture ahora forman parte de este contexto, los cambios efectuados en ellas como parte de una operación de distribuidor no persisten fuera de la operación.|  
|Sugerencia|Para solucionar este problema, pueden almacenarse los elementos CurrentCulture o CurrentUICulture deseados en un campo y protegerse todos los cuerpos de las operaciones del distribuidor (incluidos los controladores de devolución de llamadas de eventos de IU) en los que estén establecidos los elementos CurrentCulture y CurrentUICulture correctos de las aplicaciones afectadas por este cambio. Además, puesto que el cambio de ExecutionContext subyacente a este cambio de WPF afecta únicamente a las aplicaciones que tengan como destino .NET Framework 4.6 o una versión posterior, es posible evitar esta interrupción estableciendo como destino .NET Framework 4.5.2.|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0145|
