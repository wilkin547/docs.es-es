---
title: "Diagn&#243;sticos de compatibilidad de .NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: "twsouthwick"
ms.author: "tasou"
manager: "wpickett"
caps.handback.revision: 7
---
# Diagn&#243;sticos de compatibilidad de .NET
Los diagnósticos de compatibilidad de .NET son analizadores basadas en Roslyn que le ayudan a identificar problemas de compatibilidad entre las versiones de .NET Framework. Esta lista contiene todos los analizadores disponibles, aunque solo un subconjunto se aplicará a cualquier migración específica. Los analizadores determinará qué problemas son aplicables para la migración planeada y sólo mostrará aquellos. Para problemas de dividen las versiones afectadas, consulte: [compatibilidad de aplicaciones](../../../docs/framework/migration-guide/application-compatibility.md).  
  
 Cada problema incluye la siguiente información:  
  
-   La descripción de lo que ha cambiado desde una versión anterior.  
  
-   La sugerencia es una descripción de cómo el cambio afecta a los clientes y si las soluciones están disponibles para mantener la compatibilidad entre versiones.  
  
-   Una evaluación de la importancia que tiene el cambio. Problema de compatibilidad de aplicaciones se clasifican como sigue:  
  
    |||  
    |-|-|  
    |Major|Un cambio significativo que afecta a un gran número de aplicaciones o requiere una modificación sustancial del código.|  
    |Secundaria|Un cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones de código.|  
    |Caso avanzado|Un cambio que afecta a las aplicaciones en escenarios muy concretos raro.|  
    |Transparente|Un cambio con ningún efecto apreciable en el programador de la aplicación o el usuario.|  
  
-   Versión indica cuando el cambio aparece por primera vez en el marco de trabajo. Algunos de los cambios se revierten y se indica también.  
  
-   El tipo de cambio:  
  
    |||  
    |-|-|  
    |Redestinación|El cambio afecta a las aplicaciones que se vuelven a compilar una nueva versión de .NET Framework de destino.|  
    |Tiempo de ejecución|El cambio afecta a una aplicación existente que tiene como destino una versión anterior de .NET Framework, pero se ejecuta en una versión posterior.|  
  
-   Las API afectadas, si existe.  
  
-   Los identificadores de los diagnósticos disponibles  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter no puede deserializar la tabla hash y una ordenación similar objetos de colección  
  
|||  
|-|-|  
|Detalles|El SoapFormatter no garantiza que los objetos serializan en una versión deserializará correctamente en una versión diferente de .NET Framework. En concreto, algunas colecciones ordenadas (como Hashtable) agregan a miembros entre 4.0 y 4.5 tal que no se pueden deserializar objetos de estos tipos con .NET 4.0 si fueran serialzied con .NET 4.5. Tenga en cuenta que si los datos serializados se tanto serializa y deserializa con la misma versión de .NET Framework, no se producirá ningún problema.|  
|Sugerencia|Serialización de SoapFormatter debería reemplazarse con serialización BinaryFormatter o NetDataContractSerialization ser resistente a los cambios de .NET Framework.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> [SoapFormatter.Serialize (encabezado de la secuencia, objeto,\<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|Analizadores|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: elementos de plantilla de datos WPF son ahora visibles para UIA  
  
|||  
|-|-|  
|Detalles|Anteriormente, elementos de DataTemplate estaban invisibles para la automatización de la interfaz de usuario. Automatización de la interfaz de usuario a partir de 4.5, detectará estos elementos. Esto es útil en muchos casos, pero puede interrumpir las pruebas que dependen de los árboles UIA no contiene elementos de plantilla de datos.|  
|Sugerencia|Pruebas de interfaz de usuario Auomation para esta aplicación tenga actualizan para tener en cuenta el árbol UIA ahora incluyen elementos de DataTemplate previamente invisibles. Por ejemplo, las pruebas que se espera que algunos elementos que se va a ser contiguos ahora necesite esperar previamente invisibles elementos UIA entre. O las pruebas que se basan en determinados recuentos o índices para los elementos UIA tenga se actualizan con nuevos valores.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|Analizadores|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: texto de cuadro de texto WPF seleccionado aparece un color diferente cuando el cuadro de texto está inactivo  
  
|||  
|-|-|  
|Detalles|En .NET 4.5, cuando un control de cuadro de texto WPF está inactivo (no tiene el foco), el texto seleccionado dentro del cuadro aparecerá un color diferente que cuando el control está activo.|  
|Sugerencia|Comportamiento anterior de (.NET 4.0) se puede restaurar estableciendo el [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/en-us/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) propiedad en false.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analizadores|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List<>\>. ForEach puede producir la excepción cuando se modifica el elemento de lista  
  
|||  
|-|-|  
|Detalles|A partir de .NET 4.5, un `List<T>.ForEach` enumerador inicia una excepción InvalidOperationException si se modifica un elemento de la colección que realiza la llamada. Anteriormente, esto no produciría una excepción pero podría producir condiciones de carrera.|  
|Sugerencia|Idealmente, el código deberá corregirse para modificar las listas no durante la enumeración de sus elementos porque nunca es una operación segura. Para revertir al comportamiento anterior, sin embargo, una aplicación puede tener como destino .NET 4.0.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|Analizadores|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: análisis System.Uri se adhiere a RFC 3987  
  
|||  
|-|-|  
|Detalles|Análisis del URI ha cambiado de varias maneras en .NET 4.5. Sin embargo, tenga en cuenta que estos cambios sólo afectan a código destinado a .NET 4.5. Si un binario tiene como destino .NET 4.0, se tendrán en cuenta el comportamiento anterior. Cambios de análisis del URI en .NET 4.5 incluyen:<br /><br /> Análisis URI realizará la normalización y comprobación de acuerdo con las últimas reglas IRI en RFC 3987 de caracteres<br /><br /> Forma de normalización Unicode C sólo se realizará en la parte del host del URI<br /><br /> Mailto no válido: URI ahora producirán una excepción<br /><br /> Ahora se conservan los puntos finales al final de un segmento de ruta de acceso<br /><br /> `file://`URI de escape no la `?` caracteres<br /><br /> Caracteres de control Unicode `U+0080` a través de `U+009F` no son compatibles<br /><br /> Carácter de coma `,` o `%2c` no son automáticamente sin escape|  
|Sugerencia|Si la semántica de análisis anterior de .NET 4.0 URI es necesaria (a menudo no son), se puede usar dirigidas a .NET 4.0. Esto puede realizarse con un TargetFrameworkAttribute en el ensamblado, o mediante el sistema de proyectos de Visual Studio interfaz de usuario en la página de propiedades del proyecto.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|Analizadores|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: ahora escape System.Uri es compatible con RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|Detalles|URI de escape ha cambiado en .NET 4.5 para admitir [RFC 3986](http://tools.ietf.org/html/rfc3986). Entre los cambios específicos se incluyen:<br /><br /> El método `EscapeDataString` incluye los caracteres reservados entre caracteres de escape de con arreglo a RFC 3986.<br /><br /> El método `EscapeUriString` no incluye entre caracteres de escape los caracteres reservados.<br /><br /> El método `UnescapeDataString` no inicia una excepción si encuentra una secuencia de escape no válida.<br /><br /> Los caracteres de escape no reservados no se incluyen en una secuencia de escape.|  
|Sugerencia|Actualizar aplicaciones para que no se basan en UnescapeDataString a producir en el caso de una secuencia de escape no válida. Dichas secuencias deben detectarse directamente ahora.<br /><br /> De forma similar, esperar que las cadenas de Escaped y URI sin secuencias de escape y los datos pueden variar respecto a .NET 4.0 y 4.5 de .NET y no se deben comparar entre las versiones de .NET directamente. En su lugar, debe analizar y normalizadas en una única versión de .NET antes de realizan comparaciones.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|Analizadores|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: System.Net.PeerToPeer.Collaboration disponible en Windows 8  
  
|||  
|-|-|  
|Detalles|El espacio de nombres System.Net.PeerToPeer.Collaboration no está disponible en Windows 8 o superior.|  
|Sugerencia|Aplicaciones que admiten Windows 8 o superior deben actualizarse para que no dependa de este espacio de nombres o a sus miembros.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|Analizadores|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: implementar IEnumerable de catálogos de MEF y, por tanto, ya no puede utilizarse para crear un serializador  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, catálogos de MEF implementan IEnumerable y, por tanto, ya no pueden utilizarse para crear un serializador (objeto XmlSerializer). Al intentar serializar un catálogo de MEF se inicia una excepción.|  
|Sugerencia|Ya no se puede utilizar MEF para crear un serializador|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: falta el Moniker de Target Framework provoca un comportamiento 4.0  
  
|||  
|-|-|  
|Detalles|Aplicaciones sin un [TargetFrameworkAttribute](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) aplicado en el ensamblado nivel usando la semántica (modo de interpretación) de .NET Framework 4.0 se ejecutará automáticamente. Para asegurarse de alta calidad, se recomienda que todos los archivos binarios atribuirse explícitamente con un TargetFrameworkAttribute indica la versión de .NET Framework que se compilaron. Tenga en cuenta que con un moniker de framework de destino en un archivo de proyecto MSBuild para aplicar automáticamente un TargetFrameworkAttribute de caues.|  
|Sugerencia|Un [atributo de target framework](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) debe proporcionarse a través de agregar el atributo directamente al ensamblado o especificando un marco de destino en la [archivo de proyecto o GUI de propiedades del proyecto en Visual Studio](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: ya No se pueda establecer EnableViewStateMac en false  
  
|||  
|-|-|  
|Detalles|ASP.NET ya no permite a los desarrolladores especificar `<pages enableViewStateMac="false"/>` o `<@Page EnableViewStateMac="false" %>`. El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado. Sólo las aplicaciones que establezca explícitamente la propiedad EnableViewStateMac en false se ven afectadas.|  
|Sugerencia|Se debe asumir EnableViewStateMac como true y se deben resolver los errores resultantes de MAC (como se explica en [esto](https://support.microsoft.com/en-us/kb/2915218) orientación, que contiene varias resoluciones según las particularidades de la causa errores de MAC).|  
|Ámbito|Major|  
|Versión|4.5.2|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection<>\>. TryTakeFromAny ya no produce  
  
|||  
|-|-|  
|Detalles|Si una de las colecciones de entrada está marcada como completada, `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` ya no devuelve -1 y `BlockingCollection<T>.TakeFromAny` ya no produce una excepción. Este cambio permite trabajar con colecciones cuando una de las colecciones está vacía o completa y la otra colección todavía tiene elementos que se pueden recuperar.|  
|Sugerencia|Si TryTakeFromAny devolver -1 o producir TakeFromAny se usa para propósitos de flujo de control en el caso de una colección de bloqueo que se han completado, dicho código ahora debe cambiarse para usar `.Any(b => b.IsCompleted)` para detectar esta condición.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|[BlockingCollection<>\>. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analizadores|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException ahora conjuntos línea posiciones correctamente  
  
|||  
|-|-|  
|Detalles|Si el valor de LoadOptions.SetLineInfo se pasa al método Load y se produce un error de validación, las propiedades XmlSchemaException.LineNumber y XmlSchemaException.LinePosition ahora contienen información de línea.|  
|Sugerencia|Código de control de excepciones que supone XmlSchemaException.LineNumber y XmlSchemaException.LinePosition no será conjunto debe actualizarse desde estas propiedades ahora se establecerán correctamente cuando se usa SetLineInfo al cargar XML.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|Analizadores|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities es ahora de APTCA  
  
|||  
|-|-|  
|Detalles|El ensamblado está marcado con el atributo AllowPartiallyTrustedCallersAttribute.|  
|Sugerencia|Las clases derivadas no se puede marcar con SecurityCriticalAttribute. Anteriormente, los tipos derivados tenían que marcarse con SecurityCriticalAttribute. Sin embargo, este cambio no debería tener ningún impacto.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: tipos de flujo de trabajo 3.0 están obsoletos  
  
|||  
|-|-|  
|Detalles|Las API de Windows Workflow Foundation (WWF) 3.0 (los del espacio de nombres System.Workflow) están obsoletas.|  
|Sugerencia|Nuevas API de 4.0 WWF (en System.Activities) debe usarse en su lugar. Encontrará un ejemplo del uso de las nuevas API [aquí](https://msdn.microsoft.com/en-us/library/jj205427.aspx) y más orientación disponible [aquí](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx). O bien, ya que todavía se admiten las API de 3.0 WWF, se pueden utilizar y la advertencia de tiempo de compilación evita su supresión o utilizando un compilador anterior.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Redestinación|  
|Analizadores|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: algún flujo de trabajo de arrastrar y colocar las API están obsoletos  
  
|||  
|-|-|  
|Detalles|Esta API de arrastrar y colocar de flujo de trabajo está obsoleta y se producen advertencias del compilador si se vuelve a generar la aplicación frente a 4.5.|  
|Sugerencia|Nueva [DragDropHelper](https://msdn.microsoft.com/en-us/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) API que admiten operaciones con varios objetos que se deben usar en su lugar. Como alternativa, se pueden suprimir las advertencias de compilación o se puede evitar utilizando un compilador anterior. Todavía se admiten las API.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|Analizadores|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: nuevas sobrecargas Dispatcher.Invoke (ambiguas) podrían producir un comportamiento diferente  
  
|||  
|-|-|  
|Detalles|.NET Framework 4.5 agrega nuevas sobrecargas para Dispatcher.Invoke que incluyen un parámetro de tipo System.Action. Cuando se vuelve a compilar el código existente, los compiladores pueden resolver llamadas a métodos de Dispatcher.Invoke que tienen un parámetro de delegado como llamadas a métodos de Dispatcher.Invoke con un parámetro System.Action. Si una llamada a una sobrecarga de Dispatcher.Invoke con un parámetro de delegado se resuelve como una llamada a una sobrecarga de Dispatcher.Invoke con un parámetro System.Action, pueden producirse las siguientes diferencias de comportamiento:<br /><br /> Si se produce una excepción, no se generan los eventos Dispatcher.UnhandledExceptionFilter y Dispatcher.UnhandledException. En su lugar, las excepciones se controlan mediante el evento UnobservedTaskException.<br /><br /> Las llamadas a algunos miembros, como DispatcherOperation.Result, se bloquearán hasta que haya completado la operación.|  
|Sugerencia|Para evitar la ambigüedad (y las posibles diferencias en el control o el bloqueo de comportamientos de excepción), código Dispatcher.Invoke que realiza la llamada puede pasar vacía object [] como segundo parámetro a la llamada Invoke de para asegurarse de que la resolución a la sobrecarga del método .NET 4.0.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|[Dispatcher.Invoke (delegado, el objeto\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (objeto de delegado, TimeSpan,\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (objeto de delegado, el período de tiempo, DispatcherPriority,\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (objeto de delegado, DispatcherPriority,\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|Analizadores|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter constructor está obsoleto  
  
|||  
|-|-|  
|Detalles|El `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` constructor ahora está obsoleta y presentará las advertencias de compilación si se utiliza.|  
|Sugerencia|Aunque la `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` constructor seguirán funcionando, el siguiente constructor debe usarse en su lugar para evitar la advertencia de compilación obsoleta al volver a compilar el código con las herramientas de .NET 4.5: [EncoderParameter.EncoderParameter (codificador, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/en-us/library/hh875096\(v=vs.110\).aspx).|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analizadores|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: cambio de comportamiento para Task.WaitAll métodos con argumentos de tiempo de espera  
  
|||  
|-|-|  
|Detalles|Comportamiento de Task.WaitAll se realizó más coherente en .NET 4.5.<br /><br /> En .NET Framework 4, estos métodos se comportaban de forma incoherente. Cuando se agotaba el tiempo de espera, si una o más tareas se han completado o cancelado antes de la llamada al método, el método produjo una excepción de AggregateException. Cuando se agotaba el tiempo de espera, si no hay tareas se han completado o cancelado antes de la llamada al método, pero una o varias tareas entraban en estos Estados después de la llamada de método, el método devuelve false.<br />En .NET Framework 4.5, estas sobrecargas de método ahora devuelven false si las tareas siguen en ejecución cuando el intervalo de tiempo de espera expirado y producen una excepción AggregateException únicamente si se ha cancelado una tarea de entrada (independientemente de si era antes o después de la llamada al método) y no hay otras tareas se están ejecutando.|  
|Sugerencia|Si se detectó un objeto AggregateException como una forma de detectar una tarea que se canceló antes de que se invoca, la llamada de WaitAll que código en su lugar debe realizar la detección de la misma a través de la propiedad IsCanceled (por ejemplo:. Cualquier (t => t.IsCanceled)) desde .NET 4.6 sólo se producirá en ese caso, si todas las tareas en espera se completan antes del tiempo de espera.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|[Task.WaitAll (tareas\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [Task.WaitAll (tareas\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [Task.WaitAll (tareas\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analizadores|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: cambio de comportamiento en datos Definition Language (DDL) API  
  
|||  
|-|-|  
|Detalles|El comportamiento de las API de DDL cuando se especifica AttachDBFilename ha cambiado como sigue:<br /><br /> Las cadenas de conexión no necesitan especificar un valor de catálogo inicial. Anteriormente, AttatchDBFilename y el catálogo inicial se necesitaban.<br /><br /> Si se especifican AttatchDBFilename y el catálogo inicial y el archivo MDF indicado existe, el método ObjectContext.DatabaseExists devuelve true. Anteriormente, devuelve false.<br /><br /> Si se especifican AttatchDBFilename y el catálogo inicial y el archivo MDF indicado existe, una llamada al método ObjectContext.DeleteDatabase elimina los archivos.<br /><br /> Si se llama a ObjectContext.DeleteDatabase cuando la cadena de conexión especifica un valor de AttachDBFilename con un archivo MDF no existe y un catálogo inicial que no existe, el método produce una excepción InvalidOperationException. Anteriormente iniciaba una excepción SqlException.|  
|Sugerencia|Estos cambios facilitan la creación de herramientas y aplicaciones que utilizan las API de DDL. Estos cambios pueden afectar a la compatibilidad de las aplicaciones en los escenarios siguientes:<br /><br /> El usuario escribe código que se ejecuta un comando DROP DATABASE directamente en lugar de llamar a ObjectContext.DeleteDatabase si ObjectContext.DatabaseExists devuelve true. Esto interrumpe el código existente si la base de datos no está asociada pero el archivo MDF existe.<br /><br /> El usuario escribe código que espera el método ObjectContext.DeleteDatabase para producir una excepción SqlException en lugar de una excepción InvalidOperationException cuando no existe el archivo MDF y catálogo inicial.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: métodos MachineKey.Encode y MachineKey.Decode están obsoletos  
  
|||  
|-|-|  
|Detalles|Estos métodos están obsoletos. La compilación del código que llama a estos métodos genera una advertencia del compilador.|  
|Sugerencia|Las alternativas recomendadas son [MachineKey.Protect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) y [MachineKey.Unprotect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx). Como alternativa, se pueden suprimir las advertencias de compilación o se puede evitar utilizando un compilador anterior. Todavía se admiten las API.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> [MachineKey.Encode (Byte\<xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|Analizadores|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: el método de reemplazo en direcciones URL de OData está deshabilitado de forma predeterminada  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, el método de reemplazo en direcciones URL de OData está deshabilitado de forma predeterminada. Cuando reemplace OData está deshabilitado (ahora de forma predeterminada), se producirá un error en las solicitudes de usuario, incluidas las funciones de reemplazo (que son habituales).|  
|Sugerencia|Si se requiere el método replace (que es habitual), puede volver a habilitarse a través de un [configuración](https://msdn.microsoft.com/en-us/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx). Sin embargo, un método de reemplazo habilitado puede abrir puntos vulnerables de seguridad y sólo se debe utilizar después de una revisión cuidadosa.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|Analizadores|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: System.ServiceModel.Web.WebServiceHost objeto ya no agrega un extremo predeterminado  
  
|||  
|-|-|  
|Detalles|El objeto System.ServiceModel.Web.WebServiceHost ya no agrega un extremo predeterminado si se ha agregado un extremo explícito por código de aplicación.|  
|Sugerencia|Si los usuarios esperan poder conectarse a un extremo predeterminado y otros extremos explícitos se han agregado a la WebServiceHost, extremos predeterminados también se deben agregar explícitamente (mediante AddDefaultEndpoints).|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|Analizadores|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: implementaciones EventSource.WriteEvent deben pasar WriteEvent los mismos parámetros que recibió (además de Id.)  
  
|||  
|-|-|  
|Detalles|El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de EventSource que define un método de evento ETW debe llamar a la clase base al método EventSource.WriteEvent con el identificador de evento seguido por los mismos argumentos que se pasaron al método de evento ETW.|  
|Sugerencia|Se produce una excepción IndexOutOfRangeException si un EventListener lee los datos de origen de eventos en proceso para un origen de eventos que infringe este contrato.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: ahora se respeta el valor  
  
|||  
|-|-|  
|Detalles|Esta configuración establece la memoria mínima que debe estar disponible en el servidor antes de que se pueda activar un servicio WCF. Está diseñado para evitar excepciones OutOfMemoryException. En .NET Framework 4.5, este valor no tiene ningún efecto. En .NET Framework 4.5.1, se respeta este valor.|  
|Sugerencia|Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración. Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: expansión de entidades DTD XmlTextReader está limitada a 10.000.000 caracteres  
  
|||  
|-|-|  
|Detalles|Expansión de entidades DTD ya está limitada a 10.000.000 caracteres. La carga de archivos XML sin expansión de entidades DTD o con expansión de entidades DTD limitada no se verá afectada. Los archivos con entidades de DTD que se expanden a más de 10.000.000 caracteres no se podrán cargar y ahora iniciarán una excepción.|  
|Sugerencia|Si el límite de la expansión de entidades DTD es 10.000.000 demasiado bajo, se puede reemplazar el valor con el [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/en-us/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx) propiedad. Se puede pasar un XmlReaderSettings con el valor apropiado de MaxCharactersFromEntity a [XmlReader.Create](https://msdn.microsoft.com/en-us/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|Analizadores|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: cambia el mensaje de excepción de hoja de estilos XSLT  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, el texto del mensaje de error cuando un archivo XSLT es demasiado complejo es "la hoja de estilos es demasiado compleja". En versiones anteriores, el mensaje de error era “Error de compilación de XSLT”. El código de aplicación que se base en el texto del mensaje de error ya no funcionará. Sin embargo, los tipos de excepción son las mismas, por lo que este cambio no debería tener ningún impacto.|  
|Sugerencia|Actualizar el código de la aplicación según el mensaje de excepton de esta condición de error al esperar el nuevo mensaje o (mejor) actualice el código para depender únicamente del tipo de excepción ([XsltException](https://msdn.microsoft.com/en-us/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)), que no ha cambiado.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|[XslCompiledTransform.Load (MethodInfo, Byte\[\], tipo\<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|Analizadores|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF serializa Expressions.Literal<> \</> \> fechas diferente ahora (interrumpe los analizadores XAML personalizados)  
  
|||  
|-|-|  
|Detalles|Asociado [ValueSerializer](https://msdn.microsoft.com/en-us/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) objeto convertirá un valor DateTime o DateTimeOffset objeto cuyos componentes segundo y milisegundo son distintos de cero y (para una fecha y hora valor) cuya propiedad DateTime.Kind no está especificado en la sintaxis de elemento de propiedad en lugar de una cadena. Este cambio permite ser de ida y vuelta de los valores de DateTime y DateTimeOffset. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.|  
|Sugerencia|Este cambio permite ser de ida y vuelta de los valores de DateTime y DateTimeOffset. Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: nuevos valores de enumeración en PageRangeSelection de WPF  
  
|||  
|-|-|  
|Detalles|Se agregaron dos nuevos miembros (CurrentPage y SelectedPage) a la [PageRangeSelection](https://msdn.microsoft.com/en-us/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) enum.|  
|Sugerencia|En la mayoría de los casos, estos cambios no afectan a código de usuario. Llama a código que dependa de un número determinado de elementos existentes en Enum.GetNames o Enum.GetValues en el PageRangeSelection tipo debe modificarse, sin embargo.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|Analizadores|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: WPF DispatcherSynchronizationContext.CreateCopy devuelve ahora una nueva copia en lugar de la instancia actual  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4, DispatcherSynchronizationContext.CreateCopy() devuelve una referencia a la instancia actual, principalmente como una optimización del rendimiento. En .NET Framework 4.5, devuelve una nueva instancia que hace posible por primera vez a la conclusión de que las referencias iguales indican que el subproceso en ejecución está en el contexto de sincronización correcta.  Es poco probable que se verá afectado el código que comprueba la identidad de estas referencias, pero debido al cambio, el código que llama a DispatcherSynchronizationContext.CreateCopy debe probarse como parte de la migración a .NET Framework 4.5 o posterior.|  
|Sugerencia|Tenga en cuenta que DispatcherSynchronizationContext.CreateCopy() devolverá ahora un nuevo objeto de SynchronizationContext.  Anteriormente, el código que utiliza la equivalencia de referencias generado de este modo no estaba realmente comprobando si estaba en el contexto adecuado, pero cuando compilado en .NET 4.5 o posterior.  Aunque es poco probable causar problemas, ejercer las rutas de acceso de código afectado debe ser suficiente para determinar si esto plantea algún problema.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|Analizadores|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: System.Threading.Tasks.Task ya no producen ObjectDisposedException después de elimina el objeto  
  
|||  
|-|-|  
|Detalles|Excepto Task.IAsyncResult.AsyncWaitHandle, System.Threading.Tasks.Task métodos ya no producen una excepción ObjectDisposedException después de desechar el objeto.<br />Este cambio admite el uso de tareas almacenadas en memoria caché. Por ejemplo, un método puede devolver una tarea almacenada en caché para representar una operación completada en lugar de asignar una nueva tarea. Esto no era posible en versiones anteriores de .NET Framework, ya que cualquier consumidor de la tarea podía desecharla, lo que hacía que se volviera inutilizable.|  
|Sugerencia|Tenga en cuenta que los métodos de tareas ya no pueden iniciar ObjectDisposedExceptions en los casos cuando se elimina el objeto. Si una aplicación se dependiendo de que sabe que una tarea se ha cancelado esta excepción, debe actualizarse para comprobar explícitamente el estado de tarea mediante [Task.Status](https://msdn.microsoft.com/en-us/library/system.threading.tasks.task.status\(v=vs.110\).aspx).|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: excepciones diferentes para los métodos ObjectContext.CreateDatabase y DbProviderServices.CreateDatabase  
  
|||  
|-|-|  
|Detalles|A partir de .NET 4.5, si se produce un error en la creación de la base de datos, `CreateDatabase` métodos intentará quitar la base de datos vacía. Si esa operación se realiza correctamente, el original `SQLException` se propagará (en lugar de la `InvalidOperationException` que siempre se produce en .NET 4.0)|  
|Sugerencia|Cuando se detecte una excepción InvalidOperationException al ejecutar ObjectContext.CreateDatabase o DbProviderServices.CreateDatabase, SQLExceptions ahora también se deben detectar.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analizadores|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate y ObjectContext.ExecuteStoreQuery ahora admite el tipo de enumeración  
  
|||  
|-|-|  
|Detalles|En .NET 4.0, el parámetro genérico `T` de `ObjectContext.Translate` y `ObjectContext.ExecuteStoreQuery` métodos no pueden ser una enumeración. Ahora se admite este escenario.|  
|Sugerencia|Si se llamó a traducir o ExecuteStoreQuery en un tipo enum en .NET 4.0, devolvió '0'. Si este comportamiento es deseable, las llamadas deben reemplazarse por una constante 0 (o el equivalente de la enumeración de él).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|[ObjectContext.ExecuteStoreQuery<>\>(cadena, objeto\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [ObjectContext.ExecuteStoreQuery<>\>(String, String, MergeOption, objeto\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|Analizadores|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty<> \</> \> siempre devuelve en la caché de instancia  
  
|||  
|-|-|  
|Detalles|A partir de .NET 4.5, `Enumerable.Empty` siempre devuelve una instancia almacenada en caché interna `IEnumerable<T>`.<br /><br /> Anteriormente, `Enumerable.Empty` ¿caché vacía `IEnumerable<T>` en el momento en que se llamó a la API, lo que significa que en algunas condiciones en las que `Enumerable.Empty` se llamó rápidamente y de forma simultánea, diferentes instancias del tipo podrían devolverse para diferentes llamadas a la API.|  
|Sugerencia|Puesto que el comportamiento anterior era no determinista, código es improbable que dependen de él. Sin embargo, en el caso improbable de que enumerables vacíos que se comparan y espera que a veces sean iguales, se deben crear matrices vacías explícitas (`new T[0]`) en lugar de usar `Enumerable.Empty`.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|Analizadores|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: propiedad HttpRequest.ContentEncoding prohíbe UTF7  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, la codificación UTF-7 está prohibida en organismos de HttpRequests. Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.|  
|Sugerencia|Idealmente, las aplicaciones deben actualizarse para que no use la codificación UTF-7 en HttpRequests. Como alternativa, puede restaurarse comportamiento heredado mediante el uso de la `aspnet:AllowUtf7RequestContentEncoding` atributo de la [appSettings](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) elemento.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|Analizadores|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode escapes de carácter  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, JavaScriptStringEncode convierte el carácter de y comercial (&).|  
|Sugerencia|Si su aplicación depende del comportamiento anterior de este método, puede agregar una configuración de aspnet:JavaScriptDoNotEncodeAmpersand para el [elemento appSettings de ASP.NET](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) en el archivo de configuración.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener trunca las cadenas con valores null incrustados  
  
|||  
|-|-|  
|Detalles|EventListener trunca las cadenas con valores null incrustados. La clase EventSource no admiten caracteres nulos. El cambio sólo afecta a las aplicaciones que utilizan EventListener para leer los datos de origen de eventos en proceso y que utilizan caracteres null como delimitadores.|  
|Sugerencia|EventSource datos, si es posible, deben actualizarse para que no utilice caracteres nulos incrustados.|  
|Ámbito|Borde|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName> \</String, String>|  
|Analizadores|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD  
  
|||  
|-|-|  
|Detalles|Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo ObsoleteAttribute se exporta como ObsoleteAttribute y Windows.Foundation.DeprecatedAttribute.|  
|Sugerencia|Volver a compilar el código fuente existente que utiliza el atributo ObsoleteAttribute puede generar advertencias al utilizar ese código desde C++ / CX o JavaScript.<br /><br /> No se recomienda aplicar ObsoleteAttribute y Windows.Foundation.DeprecatedAttribute al código en los ensamblados administrados; puede producir advertencias de compilación.|  
|Ámbito|Borde|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|Analizadores|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: ResolveAssemblyReference (tarea) ahora advierte sobre las dependencias con la arquitectura incorrecta  
  
|||  
|-|-|  
|Detalles|La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación. Por ejemplo, esto ocurre si una aplicación que se compiló con la opción anycpu incluye un x86 referencia. Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución (en este caso, si la aplicación se implementa como un proceso x64).|  
|Sugerencia|Existen dos áreas de impacto:<br /><br /> Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild. Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.<br /><br /> Si las advertencias se tratan como errores, la aplicación no se compilará.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|Analizadores|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: tiene como valor predeterminado en el cuadro de texto WPF para deshacer el límite de 100  
  
|||  
|-|-|  
|Detalles|En .NET 4.5, el límite de deshacer predeterminado para un cuadro de texto WPF es 100 (en contraposición ilimitado en .NET 4.0)|  
|Sugerencia|Si un límite de deshacer de 100 es demasiado bajo, el límite puede establecerse explícitamente con la propiedad de UndoLimit del cuadro de texto|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analizadores|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: excepciones durante el procesamiento inadvertida en System.Threading.Tasks.Task ya no se propagan en el subproceso del finalizador  
  
|||  
|-|-|  
|Detalles|Dado que la clase System.Threading.Tasks.Task representa una operación asincrónica, detecta todas las excepciones no graves que se producen durante el procesamiento asincrónico. En .NET Framework 4.5, si no se detecta una excepción y el código nunca espera en la tarea, la excepción se ya no se propagará en el subproceso finalizador y bloqueará el proceso durante la recolección de elementos no utilizados. Este cambio mejora la confiabilidad de las aplicaciones que utilizan la clase de tarea para realizar un procesamiento asincrónico inadvertido.|  
|Sugerencia|Si una aplicación depende de las excepciones asincrónicas inadvertidas propagando en el subproceso finalizador, el comportamiento anterior puede restaurarse proporcionando un controlador adecuado para la [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/en-us/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) evento, o estableciendo un [elemento de configuración en tiempo de ejecución](https://msdn.microsoft.com/en-us/library/jj160346%28v=vs.110%29.aspx).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|Analizadores|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: propiedad IAsyncResult.CompletedSynchronously debe ser correcta para completar la tarea resultante  
  
|||  
|-|-|  
|Detalles|Al llamar a TaskFactory.FromAsync, la implementación de la propiedad IAsyncResult.CompletedSynchronously debe ser correcta para completar la tarea resultante. Es decir, la propiedad debe devolver true si y solo si la implementación se ha completado sincrónicamente. Anteriormente, esta propiedad no se comprobaba.|  
|Sugerencia|Si las implementaciones de IAsyncResult correctamente devolver true para la propiedad CompletedSynchronusly sólo cuando una tarea que se ha completado sincrónicamente, no se cuenta interrupción. Los usuarios deben revisar las implementaciones de IAsyncResult que poseen (si existe) para asegurarse de que evalúan correctamente si una tarea que se completó de forma sincrónica o no.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> </TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult>|  
|Analizadores|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: nombre de archivo de registro creado por el método ObjectContext.CreateDatabase ha cambiado para que coincidan con las especificaciones de SQL Server  
  
|||  
|-|-|  
|Detalles|Cuando el método CreateDatabase se llama directamente o mediante Code First con el proveedor SqlClient y un valor de AttachDBFilename en la cadena de conexión, se crea un archivo de registro denominado filename_log.ldf en lugar de nombreDeArchivo.ldf (donde nombre de archivo es el nombre del archivo especificado por el valor de AttachDBFilename). Este cambio mejora la depuración al proporcionar un archivo de registro cuyo nombre se ajusta a las especificaciones de SQL Server.|  
|Sugerencia|Si el nombre de archivo de registro es importante para una aplicación, la aplicación debe actualizarse para esperar el formato del nombre de archivo estándar _log.ldf.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analizadores|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: evento Page.LoadComplete ya no hace System.Web.UI.WebControls.EntityDataSource control invocar el enlace de datos  
  
|||  
|-|-|  
|Detalles|El `Page.LoadComplete` eventos ya no hace que el control de System.Web.UI.WebControls.EntityDataSource invocar el enlace de datos para los cambios en los parámetros de creación/actualización/eliminación. Este cambio elimina un viaje superfluo a la base de datos, impide que se restablezcan los valores de los controles y produce un comportamiento coherente con otros controles de datos como SqlDataSource y ObjectDataSource. Este cambio produce un comportamiento diferente en el caso improbable de que las aplicaciones invoquen el enlace de datos en el evento `Page.LoadComplete`.|  
|Sugerencia|Si es necesario para el enlace de datos, invocar manualmente databind en un evento que aparece antes en la devolución de datos.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode ya no se descodifica las secuencias de entrada no válidas  
  
|||  
|-|-|  
|Detalles|De forma predeterminada, los métodos de descodificación ya no descodifican secuencias de entrada no válidas en una cadena UTF-16 no válida. En su lugar, devuelven la entrada original.|  
|Sugerencia|El cambio en la salida del descodificador solo es importante si se almacenan datos binarios en lugar de datos UTF-16 en cadenas. Para controlar explícitamente este comportamiento, establezca la `aspnet:AllowRelaxedUnicodeDecoding` atributo de la [appSettings](https://msdn.microsoft.com/en-us/library/ms228154\(v=vs.110\).aspx) elemento a True para habilitar un comportamiento heredado o en false para habilitar el comportamiento actual.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|Analizadores|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA-256 pueden producir un error en Windows 2003  
  
|||  
|-|-|  
|Detalles|El archivo ejecutable está firmado con SHA-256. Antes se firmaba con SHA1, independientemente de si el certificado de firma de código era SHA-1 o SHA-256. Esto se aplica a lo siguiente:<br /><br /> Todas las aplicaciones compiladas con Visual Studio 2012 o versiones posteriores.<br /><br /> Aplicaciones compiladas con Visual Studio 2010 o versiones anteriores en sistemas con .NET Framework 4.5.<br /><br /> Además, si está presente .NET Framework 4.5 o versiones posteriores, el manifiesto de ClickOnce también está firmado con SHA-256 para certificados SHA-256, independientemente de la versión de .NET Framework con la que se compiló.|  
|Sugerencia|El cambio al firmar el ejecutable de ClickOnce afecta sólo los sistemas Windows Server 2003; requieren que se instale KB 938397.<br /><br /> El cambio al firmar el manifiesto con SHA-256, incluso cuando una aplicación tiene como destino .NET Framework 4.0 o versiones anteriores, introduce una dependencia de tiempo de ejecución en .NET Framework 4.5 o versiones posteriores.|  
|Ámbito|Borde|  
|Versión|4.5-4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision y DbParameter.Scale son ahora miembros virtuales públicos  
  
|||  
|-|-|  
|Detalles|DbParameter.Precision y DbParameter.Scale se implementan como propiedades públicas virtuales. Reemplazan las implementaciones de interfaz explícitas correspondientes, DbParameter.IDbDataParameter.Precision y DbParameter.IDbDataParameter.Scale.|  
|Sugerencia|Al volver a compilar un proveedor de base de datos ADO.NET, estas diferencias requerirá la palabra clave 'override' se aplica a las propiedades de escala y precisión. Esto sólo es necesario al volver a compilar los componentes; archivos binarios existentes seguirán funcionando.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|Analizadores|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData ahora recupera los datos como UTF-8  
  
|||  
|-|-|  
|Detalles|Para las aplicaciones que tienen como destino .NET Framework 4 o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, DataObject.GetData recupera los datos en formato HTML como una cadena ASCII. Como resultado, los caracteres que no son ASCII (cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios.<br /><br /> Para las aplicaciones que tienen como destino .NET Framework 4.5 o posterior y ejecución en .NET Framework 4.5.2, `DataObject.GetData` recupera los datos con formato HTML como UTF-8, que representa correctamente caracteres mayores que 0x7F.|  
|Sugerencia|Si implementa una solución para el problema de codificación mediante cadenas con formato HTML (por ejemplo, mediante la codificación explícitamente la cadena HTML recuperada del Portapapeles pasando al método UTF8Encoding.GetString) y está redestinar la aplicación desde la versión 4 a la versión 4.5, se debe quitar dicha solución alternativa.<br /><br /> Si por algún motivo, se necesita el comportamiento anterior, la aplicación puede tener como destino .NET Framework 4.0 para obtener ese comportamiento.|  
|Ámbito|Borde|  
|Versión|4.5.2|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|Analizadores|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName de dominio de aplicación predeterminado ya no tiene como valor predeterminado para null si no se establece  
  
|||  
|-|-|  
|Detalles|El TargetFrameworkName era anteriormente null en el dominio de aplicación predeterminado, a menos que se ha establecido explícitamente. A partir de 4.6, la propiedad TargetFrameworkName para el dominio de aplicación predeterminado tendrá un valor predeterminado que se deriva de TargetFrameworkAttribute (si hay alguno). Dominios de aplicación no predeterminado seguirá heredan su TargetFrameworkName de dominio de aplicación predeterminado (que no será null en 4.6) a menos que se invalide explícitamente.|  
|Sugerencia|Código debe actualizarse para que no dependa `AppDomainSetup.TargetFrameworkName` el valor predeterminado null. Si es necesario que esta propiedad seguirán se evalúa como null, puede establecerse explícitamente en ese valor.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|Analizadores|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool) no produce ahora cuando .NET no puede controlar el certificado  
  
|||  
|-|-|  
|Detalles|Anteriormente, este método podría producir si se pasó a 'true' para el parámetro verbose y no hay certificados instalados que no eran compatibles con .net Framework. Ahora, el método se realice correctamente y devuelva una cadena válida que omite las partes inaccesibles del certificado.|  
|Sugerencia|Cualquier código de la función X509Certificate2.ToString(bool) debe actualizarse para esperar que la cadena devuelta puede excluir algunos datos de certificado (por ejemplo, la clave pública, clave privada y extensiones) en algunos casos en que hubiera generado previamente la API.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: objetos de reflexión ya no se pueden pasar desde código administrado a los clientes DCOM fuera de proceso  
  
|||  
|-|-|  
|Detalles|Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Se ven afectados los siguientes tipos:<br /><br /> Assembly<br /><br /> MemberInfo (y sus tipos derivados, incluidos FieldInfo, MethodInfo, tipo y TypeInfo)<br /><br /> MethodBody<br /><br /> Módulo<br /><br /> ParameterInfo.<br /><br /> Las llamadas a `IMarshal` para el objeto devuelto `E_NOINTERFACE`.|  
|Sugerencia|Actualizar el código de cálculo de referencias para trabajar con objetos de reflexión no|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition DateTimes devuelve la cadena ligeramente diferente  
  
|||  
|-|-|  
|Detalles|Se han actualizado las representaciones de cadena de ContentDispositions a partir de 4.6 a siempre representan el componente de hora de una fecha y hora con dos dígitos. Esto es para cumplir con [RFC822](http://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](http://www.ietf.org/rfc/rfc2822.txt). Esto hace que `ContentDisposition.ToString` para devolver una cadena algo diferente en 4.6 en escenarios donde uno de los elementos de tiempo de eliminación estaba antes de 10:00 AM. Tenga en cuenta que ContentDispositions a veces se serializan a través de convertirlas en cadenas, por lo que las operaciones de ContentDisposition ToString, serialización o llamadas GetHashCode deben revisarse.|  
|Sugerencia|No espera que las representaciones de cadena de ContentDispositions de distintas versiones de .NET Framework se compararán correctamente entre sí. Convertir las cadenas a ContentDispositions, si es posible, antes de realizar una comparación.|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|Analizadores|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load no quitar una propiedad de símbolo  
  
|||  
|-|-|  
|Detalles|Cuando el destino es .NET Framework 4.5 en el Diseñador de flujo de trabajo y cargar un flujo de trabajo 3.5 hospedado con el método WorkflowDesigner.Load(), se produce un XamlDuplicateMemberException al guardar el flujo de trabajo.|  
|Sugerencia|Este error sólo se presenta cuando el destino es .NET Framework 4.5 en el Diseñador de flujo de trabajo, por lo que puede solucionar estableciendo la `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` a .NET Framework 4.0.<br /><br /> Como alternativa, se puede evitar el problema mediante el uso de la [WorkflowContext.Load(string)](https://msdn.microsoft.com/en-us/library/ee425926\(v=vs.110\).aspx) para cargar el flujo de trabajo, en lugar de [WorkflowDesigner.Load()](https://msdn.microsoft.com/en-us/library/ee403482\(v=vs.110\).aspx).|  
|Ámbito|Major|  
|Versión|4.5-4.5.2|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|Analizadores|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open genera un error en Windows 7 con IFS Winsock BSP o LSP presente  
  
|||  
|-|-|  
|Detalles|Si se ejecuta en un equipo con Windows 7 con IFS Winsock BSP o LSP está presente en el equipo, no SqlConneciton.Open y OpenAsync en .NET Framework 4.5.<br /><br /> Para determinar si está instalado un no IFS BSP o LSP, utilice la `netsh WinSock Show Catalog` comando y examine cada `Winsock Catalog Provider Entry` elemento devuelto. Si el valor de indicadores de servicio tiene la `0x20000` bit establecido, el proveedor utiliza identificadores IFS y funcionará correctamente. Si el `0x20000` bits está desactivado (no establecido), es un no IFS BSP o LSP.|  
|Sugerencia|Este error se ha corregido en .NET Framework 4.5.2, por lo que se puede evitar mediante la actualización de .NET Framework. Como alternativa, puede evitarse mediante la eliminación de cualquier instalado LSP de Winsock no - IFS.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5.2|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|Analizadores|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: comportamiento de evento ICommand.CanExecuteChanged por mi propia cambió en .NET 4.5  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, se omitió un CanExecuteChangedEvent a menos que el remitente del evento era el mismo objeto que el objeto que provocó el evento. Este error se corrigió en .NET Framework 4.5 servcing actualizaciones.|  
|Sugerencia|Este error se ha corregido en .NET Framework 4.5 para el mantenimiento de versiones, por lo que puede evitarse si se asegura de que .NET Framework está actualizada o actualizando a .NET Framework 4.5.1. Como alternativa, puede modificarse mediante ICommand código de la aplicación para asegurarse de que el remitente al generar un comando CanExecuteChanged es el mismo que el objeto que provoca el evento.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|Analizadores|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: algunas API de .NET hacer la primera oportunidad (controlado) EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, un pequeño número de métodos de .NET empezaron a producir EntryPointNotFoundExceptions de primera oportunidad. Estas excepciones se controlan dentro de .net Framework, pero podría interrumpir la automatización de prueba que no esperaba las excepciones de primera oportunidad. Estas mismas API interrumpen algunos escenarios ApiVerifier cuando HighVersionLie está habilitado.|  
|Sugerencia|Este error puede evitarse con la actualización a .NET Framework 4.5.1. Como alternativa, automatización de prueba puede actualizarse para no interrumpir EntryPointNotFoundExceptions de primera oportunidad.|  
|Ámbito|Borde|  
|Versión|4.5-4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> [Debug.Assert (Boolean, String, String, Object\<xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|Analizadores|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: el desplazamiento de TreeView de WPF o ListBox agrupado en un VirtualizingStackPanel puede producir una falta de respuesta  
  
|||  
|-|-|  
|Detalles|En v4.5 de .NET Framework, al desplazarse de un control TreeView de WPF en un panel de apilamiento virtualizado puede provocar bloqueos, si hay márgenes en la ventanilla (entre los elementos de la vista de árbol, por ejemplo, o en un elemento ItemsPresenter). Además, en algunos casos, diferentes elementos con tamaño de la vista pueden causar la inestabilidad incluso si no hay márgenes.|  
|Sugerencia|Este error puede evitarse con la actualización a .NET Framework 4.5.1. Como alternativa, pueden quitarse los márgenes de colecciones de vista (como los controles TreeView) dentro de paneles de apilamiento virtualizado si todos los elementos contenidos son del mismo tamaño.|  
|Ámbito|Major|  
|Versión|4.5-4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom devuelve un resultado incorrecto para las variables genéricos con restricciones  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, se devolverá incorrectamente Type.IsAssignableFrom `false` en todos los casos para algunos tipos genéricos con restricciones.|  
|Sugerencia|Este problema se corrigió en una actualización. Actualice .NET Framework 4.5, o actualizar a .NET Framework 4.5.1 o posterior, para corregir este problema. Como alternativa, evite utilizar IsAssignableFrom con tipos genéricos que tienen restricciones en parámetros genéricos. API de reflexión pueden utilizarse como una solución alternativa.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|Analizadores|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: Entity Framework 6.0 carga muy lentamente en las aplicaciones iniciadas desde Visual Studio  
  
|||  
|-|-|  
|Detalles|Iniciar una aplicación desde Visual Studio 2013 que utiliza Entity Framework 6.0 puede ser muy lento.|  
|Sugerencia|Este problema se corrigió en Entity Framework 6.0.2. Actualice Entity Framework para evitar el problema de rendimiento.|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: espaciado de cuadro de texto multilínea ASP.Net cambia al usar AntiXSSEncoder  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.0, las líneas adicionales se insertaron entre líneas de un cuadro de texto de varias líneas de devolución de datos, si utiliza el `AntiXSSEncoder`. En .NET Framework 4.5, los saltos de línea adicionales no están incluidos, pero sólo si la aplicación web está destinada a .NET 4.5|  
|Sugerencia|Tenga en cuenta que las aplicaciones web 4.0 redestinadas a .NET 4.5 pueden tener mejorados para no insertar saltos de línea adicionales de cuadros de texto de varias líneas. Si esto no es deseable, la aplicación puede tener el comportamiento anterior cuando se ejecuta en .NET Framework 4.5 dirigidas a .NET Framework 4.0.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Redestinación|  
|Analizadores|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue<>\>. TryPeek puede devolver un valor null erróneo a través de su parámetro out  
  
|||  
|-|-|  
|Detalles|En algunos escenarios multiproceso, `ConcurentQueue<T>.TryPeek` puede devolver true pero rellenar el parámetro de salida con un valor null (en lugar del valor correcto, inspeccionado).|  
|Sugerencia|Este problema está corregido en .NET Framework 4.5.1. Actualización a ese marco de trabajo, se solucionará el problema.|  
|Ámbito|Major|  
|Versión|4.5-4.5.1|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|Analizadores|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: pueden volver a organizar varios elementos en una sola celda de TableLayoutPanel  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, si varios elementos se colocan en la misma celda de TableLayoutPanel, se puede mostrar en un orden diferente que estuvieran en .NET Framework 4.0.|  
|Sugerencia|Este comportamiento se revirtió en una actualización para .NET Framework 4.5. Actualice .NET Framework 4.5, o actualizar a .NET Framework 4.5.1 o posterior, para corregir este problema. Como alternativa, evitar el caso de varios elementos en la misma celda TableLayourPanel ambiguo.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analizadores|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: variable de iterador Foreach ahora dentro del ámbito de la iteración, por lo que es diferente (en C#&5;) captura semántica de cierre  
  
|||  
|-|-|  
|Detalles|A partir de C# 5 (Visual Studio 2012), variables de iteración foreach tienen el ámbito de la iteración. Esto puede provocar saltos si código previamente se dependiendo de las variables que no se incluirán en el cierre de foreach. El síntoma de este cambio es que una variable de iterador pasada a un delagate se tratará como el valor que tenía en el momento en que se creó el delegado, en lugar del valor que tenía en el momento en que se invoca el delegado.|  
|Sugerencia|Idealmente, el código debe actualizarse para esperar el nuevo comportamiento del compilador. Si se requieren la semántica anterior, la variable de iterador se puede reemplazar por una variable independiente que explícitamente se coloca fuera del ámbito del bucle.|  
|Ámbito|Major|  
|Versión|4.5|  
|Tipo|Redestinación|  
|Analizadores|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: no representar el HtmlTextWriter\`<br>\>' elemento correctamente  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.6, llamar a `HtmlTextWriter.RenderBeginTag()` y `HtmlTextWriter.RenderEndTag()` con una `<BR />` elemento insertará correctamente solo una `<BR />` (en lugar de dos)|  
|Sugerencia|Si una aplicación dependía de ácido `<BR />` etiqueta `HtmlTextWriter.RenderBeginTag()` debe llamarse una segunda vez. Tenga en cuenta que cambiar este comportamiento sólo afecta a las aplicaciones que están destinadas a .NET Framework 4.6, por lo que la otra opción consiste en una versión anterior de .NET Framework de destino con el fin de obtener el comportamiento anterior.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|Analizadores|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: Items.Refresh de llamada en un ListBox de WPF, ListView o DataGrid con los elementos seleccionados para hacer que los elementos duplicados que aparezca en el elemento  
  
|||  
|-|-|  
|Detalles|En .NET Framework 4.5, llamar a ListBox.Items.Refresh desde el código, mientras que los elementos seleccionados en un control ListBox para hacer que los elementos seleccionados se duplique en la lista. Se produce un problema similar con ListView y DataGrid. Esto está corregido en .NET Framework 4.6.|  
|Sugerencia|Este problema se puede solucionar anulando la selección de elementos mediante programación antes de llama a la actualización y seleccionando a continuación volver a ellas después de que se complete la llamada. O bien, este problema se ha corregido en .NET Framework 4.6 y se puede solucionar con la actualización a esa versión de .NET Framework.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|Analizadores|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: EventListeners ETW no capturar los eventos de proveedores con palabras clave explícita (como el proveedor de la biblioteca TPL)  
  
|||  
|-|-|  
|Detalles|ETW EventListeners con una máscara de palabra clave en blanco no capturar correctamente los eventos de proveedores con palabras clave explícita. En .NET Framework 4.5, el proveedor TPL comenzó a ofrecer palabras clave explícita y desencadena este problema. En .NET Framework 4.6 EventListeners se actualizaron para ya no tienen este problema.|  
|Sugerencia|Para evitar este problema, reemplace llamadas a EnableEvents (eventSource nivel) con llamadas a la sobrecarga de EnableEvents que especifique explícitamente la máscara "todas las palabras clave" que se va a utilizar: `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`.<br /><br /> O bien, este problema se ha corregido en .NET Framework 4.6 y se puede solucionar con la actualización a esa versión de .NET Framework.|  
|Ámbito|Borde|  
|Versión|4.5-4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|Analizadores|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: compilar un edmx Entity Framework con Visual Studio 2013 puede producir el error MSB4062 si mediante las tareas EntityDeploySplit o EntityClean  
  
|||  
|-|-|  
|Detalles|Herramientas de MSBuild 12.0 (incluidos en Visual Studio 2013) cambiado de ubicación de archivo de msbuild, causando antiguos archivos de destino de Entity Framework no es válido. El resultado es que `EntityDeploySplit` y `EntityClean` tareas producirá un error porque no pueden encontrar `Microsoft.Data.Entity.Build.Tasks.dll`. Tenga en cuenta que este salto debido a un cambio del conjunto de herramientas (msbuild/VS), no es debido a un cambio de .NET Framework. Sólo se producirá al actualizar las herramientas de desarrollo, no cuando simplemente actualizar .NET Framework.|  
|Sugerencia|Archivos de destino de Entity Framework se corrigen para que funcione con el principio de diseño de msbuild nuevo en .NET Framework 4.6. Actualizar a esa versión de Framework se solucionará este problema. O bien, [esto](http://stackoverflow.com/a/24249247/131944) solución alternativa se puede utilizar para aplicar revisiones a los archivos de destino directamente.|  
|Ámbito|Major|  
|Versión|4.5.1-4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: validación de esquema XSD ahora detecta correctamente las infracciones de restricciones unique si se utilizan las claves compuestas y una clave está vacía  
  
|||  
|-|-|  
|Detalles|Versiones de .NET Framework anteriores a 4.6 tenían un error que provocó la validación XSD que no se detecten restricciones únicas en las claves compuestas si una de las claves estaba vacía. En .NET Framework 4.6, este problema se ha corregido. Esto dará como resultado de validación más correcta, pero también puede provocar algunos datos XML no se validan que previamente habría.|  
|Sugerencia|Si es más flexible, es necesaria la validación de .NET Framework 4.0, la aplicación de validación puede tener como destino versión 4.5 (o anterior) de .NET Framework. Hora de redestinación en .NET 4.6, sin embargo, la revisión de código debe realizarse para asegurarse de que las claves compuestas duplicadas (como se describe en la descripción de la salida) no se esperan que validar.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: Attribute.GetCustomAttributes llamada en una propiedad de indizador ya no produce AmbiguousMatchException si se puede resolver la ambigüedad por tipo de índice  
  
|||  
|-|-|  
|Detalles|Antes de .NET Framework 4.6, llamar a `GetCustomAttribute(s)` en un indizador, propiedad que difiere de otra propiedad sólo por el tipo del índice resultaría en una `AmbiguousMatchException`. A partir de .NET Framework 4.6, atributos de la propiedad devuelva correctamente.|  
|Sugerencia|Tenga en cuenta que GetCustomAttribute(s) funcionará con más frecuencia ahora. Si una aplicación previamente se basa en el `AmbiguousMatchException`, ahora se debe usar la reflexión para buscar explícitamente varios indizadores, en su lugar.|  
|Ámbito|Borde|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: intermitentemente no puede desplazarse al elemento de la parte inferior de ItemsControl (como ListBox y DataGrid) al usar DataTemplates personalizado  
  
|||  
|-|-|  
|Detalles|En algunos casos, un error en .NET Framework 4.5 está causando ItemsControl (por ejemplo, ListBox, ComboBox, DataGrid, etc.) que no vaya a su elemento de la parte inferior al usar DataTemplates personalizado. Si el desplazamiento se intenta una segunda vez (después de desplazarse hacia arriba), que funciona a continuación.|  
|Sugerencia|Este problema se ha corregido en .NET Framework 4.5.2 y se puede solucionar con la actualización a esa versión (o una versión posterior) de .NET Framework. Como alternativa, los usuarios aún pueden arrastrar las barras de desplazamiento para los elementos finales de estas colecciones, pero que necesite probar dos veces hacerlo correctamente.|  
|Ámbito|Secundaria|  
|Versión|4.5-4.5.2|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent devuelven valores diferentes a partir de .NET 4.5  
  
|||  
|-|-|  
|Detalles|Se realizaron mejoras en GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent en .NET Framework 4.5 para resolver problemas en los cuadros eran demasiado pequeños para los glifos contenidos en algunos casos, en .NET Framework 4.0. Como resultado, algunos cuadros de límite será mayor a partir de .NET Framework 4.5, lo que resulta en sutiles diferencias en el diseño de la interfaz de usuario.|  
|Sugerencia|Tenga en cuenta que algunos tamaños de cuadro de límite de glifo han aumentado. Estos cambios mejorarán normalmente presentación y las pruebas de posicionamiento del cuadro, pero si se desea el comportamiento anterior de (anteriores a .NET 4.5), se puede optar por agregando la entrada siguiente al archivo app.config:<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|Analizadores|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: llamar a DataGrid.CommitEdit desde un controlador de CellEditEnding quita el foco  
  
|||  
|-|-|  
|Detalles|Llamada a DataGrid.CommitEdit desde uno de los controladores de eventos del control DataGrid CellEditEnding hace que el control DataGrid pierde el foco.|  
|Sugerencia|Este error se ha corregido en .NET Framework 4.5.2, por lo que se puede evitar mediante la actualización de .NET Framework. Como alternativa, puede evitarse explícitamente volviendo a seleccionar el control DataGrid después de llamar a CommitEdit.|  
|Ámbito|Borde|  
|Versión|4.5-4.5.2|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analizadores|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC ahora escapes de espacios de cadenas que se pasa a través de parámetros de ruta  
  
|||  
|-|-|  
|Detalles|Para cumplir con RFC 2396, espacios en las rutas de acceso ahora se escapan al rellenar los parámetros de acción de una ruta. Por lo tanto, mientras que `/controller/action/some data` previamente coincidiría con la ruta `/controller/action/{data}` y proporcionar `some data` como el parámetro de datos proporcionará ahora `some%20data` en su lugar.|  
|Sugerencia|Código debe actualizarse para unescape parámetros de cadena de una ruta. Si se necesita el identificador URI original, puede tener acceso a la API Request.RequestUri.OriginalString.|  
|Ámbito|Secundaria|  
|Versión|4.5.2|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Web.Http.RouteAttribute.%23ctor%28System.String%29?displayProperty=fullName>|  
|Analizadores|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET ya no admite la calificación de espacio de nombres parciales para System.Windows APIs  
  
|||  
|-|-|  
|Detalles|A partir de .NET 4.5.2, VB.NET proyectos no pueden especificar System.Windows APIs con espacios de nombres parcialmente calificados. Por ejemplo, que hace referencia a `Windows.Forms.DialogResult` se producirá un error. En su lugar, el código debe hacer referencia para el nombre completo (`System.Windows.Forms.DialogResult`) o para importar el espacio de nombres específico y consulte simplemente a `DialogResult`.|  
|Sugerencia|Debe actualizarse el código para hacer referencia a `System.Windows` API simple nombres (e importar el espacio de nombres pertinente) o de nombres completos.|  
|Ámbito|Secundaria|  
|Versión|4.5.2|  
|Tipo|Redestinación|  
|Analizadores|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: no se admite el enlace de datos bidireccional a una propiedad con un establecedor no públicos  
  
|||  
|-|-|  
|Detalles|Intento de enlazar los datos a una propiedad sin un establecedor público nunca ha sido un escenario admitido. A partir de .NET Framework 4.5.1, este escenario, producirá una excepción InvalidOperationException. Tenga en cuenta que sólo se producirá esta excepción nueva para aplicaciones específicamente destinadas a .NET Framework 4.5.1. Si una aplicación tiene como destino .NET Framework 4.5, se permitirá la llamada. Si la aplicación no tiene como destino una versión concreta de .NET Framework, el enlace se tratarán como unidireccionales.|  
|Sugerencia|La aplicación debe actualizarse para utilizar el enlace unidireccional o exponer públicamente de establecedor de la propiedad. Como alternativa, establecer .NET Framework 4.5 provocará la aplicación para mostrar el comportamiento anterior.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|Analizadores|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf y Marshal.PtrToStructure código dinámico de salto de sobrecargas  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5.1, enlazar dinámicamente a los métodos `Marshal.SizeOf` o `Marshal.PtrToStructure` (a través de Windows PowerShell, IronPython o la dinámica palabra clave C#, por ejemplo) puede dar lugar a `MethodInvocationExceptions` porque se han agregado nuevas sobrecargas de estos métodos que podrían ser ambiguas a los motores de secuencias de comandos.|  
|Sugerencia|Actualización de scripts para indicar claramente qué debe ser de sobrecarga utiliza. Esto puede que se suele realizar mediante la conversión explícita de parámetros de tipo de los métodos como `System.Type`. Consulte [este vínculo](https://support.microsoft.com/en-us/kb/2909958/) para obtener más detalles y ejemplos de cómo para solucionar el problema.|  
|Ámbito|Secundaria|  
|Versión|4.5.1|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus llama repetidamente si su controlador muestra un cuadro de mensaje de formularios Windows Forms  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.5, llamar a `System.Windows.Forms.MessageBox.Show` de un `UIElement.PreviewLostKeyboardFocus` controlador hará que el controlador volver a activar cuando se cierra el cuadro de mensaje, lo que podría provocar un bucle infinito de cuadros de mensaje.|  
|Sugerencia|Hay dos opciones para evitar este problema:<br /><br /> Se puede evitar mediante una llamada a `System.Windows.MessageBox.Show` en lugar de `System.Windows.Forms.MessageBox.Show`.<br /><br /> Se puede evitar mostrando el cuadro de mensaje de un `LostKeyboardFocus` controlador de eventos (como oposición a un `PreviewLostKeyboardFocus` controlador de eventos).|  
|Ámbito|Borde|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|Analizadores|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: no se puede deserializar ConcurrentDictionary serializado en .NET 4.5 con NetDataContractSerializer por .NET 4.5.1 o 4.5.2  
  
|||  
|-|-|  
|Detalles|Debido a cambios internos en el tipo, `System.Collections.Concurrent.ConcurrentDictionary` objetos que se serializan con .NET Framework 4.5 con la `NetDataContractSerializer` no se puede deserializar en .NET Framework 4.5.1 o en .NET Framework 4.5.2.<br /><br /> Tenga en cuenta que el traslado de la otra dirección (serializar con .NET Framework 4.5 y deserializar con .NET Framework 4.5) funciona. Del mismo modo, toda la serialización entre versiones 4.x funciona con .NET Framework 4.6.<br /><br /> Serialización y deserialización de una única versión de .NET Framework no se ve afectado.|  
|Sugerencia|Si es necesario serializar y deserializar ConcurrentDictionary entre .NET Framework 4.5 y 4.5.1/4.5.2 .NET Framework, debe utilizarse un serializador alternativo como el serializador DataContractSerializer o BinaryFormatter en lugar de NetDataContractSerializer.<br /><br /> O bien, porque se soluciona este problema en .NET Framework 4.6, puede resolverse mediante la actualización a esa versión de .NET Framework.|  
|Ámbito|Secundaria|  
|Versión|4.5.1-4.6|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: calendario persa ahora usa el algoritmo Hijri solar  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.6, la clase de calendario persa utiliza el algoritmo Hijri solar. Convertir fechas del calendario persa entre otros calendarios puede producir un principio resultados ligeramente diferente con .NET Framework 4.6 para las fechas anteriores a 1800 o posteriores a 2023 (gregoriano).<br /><br /> Además, `PersianCalendar.MinSupportedDateTime` es ahora `March 22, 0622 instead of March 21, 0622`.|  
|Sugerencia|Tenga en cuenta que algunas fechas tardías o tempranos pueden ser ligeramente diferentes al usar el calendario persa en .NET 4.6. Además, al serializar las fechas entre los procesos que se pueden ejecutar en distintas versiones de .NET Framework, no almacenarlas como cadenas de fecha del calendario persa (dado que esos valores pueden ser diferentes).|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Tiempo de ejecución|  
|API afectadas|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|Analizadores|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: llamada CreateDefaultAuthorizationContext con un argumento null ha cambiado  
  
|||  
|-|-|  
|Detalles|La implementación de AuthorizationContext devuelto por una llamada a la `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` con una authorizationPolicies null argumento ha cambiado su implementación en .NET Framework 4.6.|  
|Sugerencia|En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento. En tales casos, el comportamiento anterior puede restaurarse de dos maneras:<br /><br /> Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6. Servicios hospedados por IIS, utilice la <httpRuntime targetframework="x.x"></httpRuntime> \> elemento como destino una versión anterior de .NET Framework.<br /><br /> Agregue la siguiente línea a la `<appSettings>` sección del archivo app.config:`<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|Analizadores|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: WPF TreeViewItem debe utilizarse dentro de un control TreeView  
  
|||  
|-|-|  
|Detalles|Se introdujo un cambio en 4.5 que restringe el uso de elementos de TreeViewItem fuera de un control TreeView. Esto se manifiesta en las siguientes condiciones:<br /><br /> Elemento primario visual de TreeViewItem no es un panel. (Un TreeViewItem generado para un control TreeView tendrá un panel como su elemento primario)<br /><br /> El TreeViewItem es un descendiente de un VirtualizingStackPanel actúa como el "host de elementos" para un control de lista (ListBox, DataGrid, ListView, etcetera). La virtualización no debe estar habilitados.<br /><br /> El VirtualizingStackPanel es el desplazamiento de elemento (`ScrollUnit="Item"`).<br /><br /> Alguien llama `VirtualizingStackPanel.MakeVisible(v)` para desplazarse de un elemento `v` en la vista. Esto puede hacerse explícita o implícitamente, en una de varias maneras; quizás el más común forma es simplemente haciendo clic en `v` para dar el foco del teclado.<br /><br /> La cadena primaria visual desde `v` a las pasadas VirtualizingStackPanel a través de la TreeViewItem.<br /><br /> En otras palabras, esto se ve cuando se usa un TreeViewItem fuera de una vista de árbol y el usuario hace clic en un descendiente de la TreeViewItem para incluirlos en la vista. Si el TreeViewItem no tiene ningún descendiente puede recibir el foco, nunca verá este problema. Un ejemplo de una situación donde esto se visita es cuando un TreeViewItem es la raíz de una plantilla de datos.  Cuando se alcanza este problema, hay una excepción InvalidCastException que tiene lugar en el marco WPF.|  
|Sugerencia|Una revisión estará disponible para este.|  
|Ámbito|Secundaria|  
|Versión|4.5|  
|Tipo|Tiempo de ejecución|  
|Analizadores|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims considera que sus claimTypes todos  
  
|||  
|-|-|  
|Detalles|En las aplicaciones que tienen como destino .NET Framework 4.6.1, si un X509 conjunto de notificaciones se inicializa a partir de un certificado que tenga varias entradas DNS en su campo de SAN, el método FindClaims intenta hacer coincidir el argumento claimType con todas las entradas DNS.<br /><br /> Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, el método FindClaims intenta coincidir con el argumento claimType sólo con la última entrada DNS.|  
|Sugerencia|Este cambio sólo afecta a las aplicaciones destinadas a .NET Framework 4.6.1. Este cambio puede estar deshabilitado (o habilitado si destino pre-4.6.1) con el [DisableMultipleDNSEntries](https://msdn.microsoft.com/en-us/library/mt620030%28v=vs.110%29.aspx) modificador de compatibilidad.|  
|Ámbito|Secundaria|  
|Versión|4.6.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|Analizadores|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage ya no se produce para las implementaciones de reentrada de IMessageFilter.PreFilterMessage  
  
|||  
|-|-|  
|Detalles|Antes de .NET Framework 4.6.1, la llamada a Application.FilterMessage con un IMessageFilter.PreFilterMessage qué AddMessageFilter llamado o RemoveMessageFilter (mientras se llama a Application.DoEvents) provocará una excepción IndexOutOfRangeException.<br /><br /> A partir de las aplicaciones destinadas a .NET Framework 4.6.1, esta excepción ya no se inicia y reentrantes filtros pueden usarse como se describió anteriormente.|  
|Sugerencia|Tenga en cuenta que Application.FilterMessage ya no se producirá para el comportamiento de IMessageFilter.PreFilterMessage reentrante descrito anteriormente. Esto solo afecta a las aplicaciones destinadas a .NET Framework 4.6.1.<br /><br /> Aplicaciones dirigidas a .NET Framework 4.6.1 pueden optar por este cambio (o destinatarios marcos más antiguos pueden participar en las aplicaciones) usando el [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/en-us/library/mt620032%28v=vs.110%29.aspx) modificador de compatibilidad.|  
|Ámbito|Borde|  
|Versión|4.6.1|  
|Tipo|Redestinación|  
|API afectadas|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|Analizadores|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture no se conserva en las operaciones del distribuidor de WPF  
  
|||  
|-|-|  
|Detalles|A partir de .NET Framework 4.6, realizan cambios CurrentCulture o CurrentUICulture dentro de un [distribuidor](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) se perderán al final de esa operación del distribuidor. De forma similar, los cambios CurrentCulture o CurrentUICulture realizadas fuera de una operación de distribuidor podrían no reflejarse cuando que se ejecuta la operación.<br /><br /> Hablando de forma práctica, esto significa que los cambios de CurrentCulture y CurrentUICulture no fluya entre las devoluciones de llamada de la UI de WPF y otro código en una aplicación WPF.<br /><br /> Esto es debido a un cambio en [ExecutionContext](https://msdn.microsoft.com/en-us/library/system.threading.executioncontext%28v=vs.110%29.aspx) que hace que CurrentCulture y CurrentUICulture se almacenen en el comienzo del contexto de ejecución con aplicaciones destinadas a .NET Framework 4.6. Las operaciones del distribuidor WPF almacenan el contexto de ejecución que se utiliza para iniciar la operación y restaurar el contexto anterior cuando se complete la operación. Dado que CurrentCulture y CurrentUICulture ahora forman parte de ese contexto, no se conservan los cambios dentro de una operación de distribuidor fuera de la operación.|  
|Sugerencia|Aplicaciones afectadas por este cambio pueden solucionarlo almacenando CurrentCulture deseado o cuerpos CurrentUICulture en un campo y la comprobación en todas las operaciones del distribuidor (incluidos los controladores de devolución de llamada de evento de interfaz de usuario) que se establecen los correctos CurrentCulture y CurrentUICulture. O bien, porque ExecutionContext cambiar subyacente este cambio WPF sólo afecta a las aplicaciones para .NET Framework 4.6 o posterior, se puede evitar esta interrupción dirigidas a .NET Framework 4.5.2.|  
|Ámbito|Secundaria|  
|Versión|4.6|  
|Tipo|Redestinación|  
|Analizadores|CD0145|