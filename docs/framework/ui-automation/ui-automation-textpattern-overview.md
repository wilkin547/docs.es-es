---
title: Información general sobre el modelo de texto de UI Automation
description: Lea información general sobre el patrón de control TextPattern en la automatización de la interfaz de usuario. Este patrón de control expone el contenido textual de un control, incluido el formato y el estilo.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, TextPattern class
- TextPattern class
- classes, TextPattern
ms.assetid: 41787927-df1f-4f4a-aba3-641662854fc4
ms.openlocfilehash: 986b601bbd212582c09c559a9bb22983ba59fa17
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924674"
---
# <a name="ui-automation-textpattern-overview"></a>Información general sobre el modelo de texto de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

Esta información general describe cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para exponer el contenido textual, incluidos los atributos de estilo y formato, de los controles de texto en plataformas compatibles con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Estos controles incluyen, entre otros, el marco de Microsoft .NET y, <xref:System.Windows.Controls.TextBox> así <xref:System.Windows.Controls.RichTextBox> como sus equivalentes de Win32.

Exponer el contenido textual de un control se logra mediante el uso del patrón de control <xref:System.Windows.Automation.TextPattern> , que representa el contenido de un contenedor de texto como una secuencia de texto. A su vez, <xref:System.Windows.Automation.TextPattern> requiere el soporte de la clase <xref:System.Windows.Automation.Text.TextPatternRange> para exponer atributos de formato y estilo. <xref:System.Windows.Automation.Text.TextPatternRange> da soporte a <xref:System.Windows.Automation.TextPattern> mediante la representación de intervalos de texto contiguos, múltiples o no contiguos en un contenedor de texto con una colección de extremos <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> y <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> . <xref:System.Windows.Automation.Text.TextPatternRange> admite la funcionalidad como selección, comparación, recuperación y exploración transversal.

> [!NOTE]
> Las clase <xref:System.Windows.Automation.TextPattern> no proporcionan un medio para insertar o modificar texto. Sin embargo, dependiendo del control, esto puede realizarse mediante [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <xref:System.Windows.Automation.ValuePattern> o a través de la entrada de teclado directa. Vea [TextPattern Insert Text Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText) para obtener un ejemplo.

La funcionalidad descrita en este artículo es vital para los proveedores de tecnología de asistencia y sus usuarios finales. Las tecnologías de asistencia pueden usar [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para recopilar información de formato de texto para el usuario y proporcionar navegación y selección de texto mediante programación por <xref:System.Windows.Automation.Text.TextUnit> (carácter, palabra, línea o párrafo).

<a name="UI_Automation_TextPattern_vs__Cicero"></a>

## <a name="ui-automation-textpattern-vs-text-services-framework"></a>TextPattern de automatización de la interfaz de usuario versus Text Services Framework (TSF)

Text Services Framework (TSF) es un marco de trabajo del sistema simple y escalable que habilita los servicios de lenguaje natural y la entrada de texto avanzada en el escritorio y en las aplicaciones. Además de proporcionar interfaces para aplicaciones para exponer su almacén de texto, también admite metadatos para ese almacén de texto.

Sin embargo, TSF se diseñó para aplicaciones que necesitan insertar entradas en escenarios de contexto, mientras que <xref:System.Windows.Automation.TextPattern> es una solución de solo lectura (con la solución limitada indicada anteriormente) pensada para proporcionar acceso optimizado a un almacén de texto para los lectores de pantalla y los dispositivos Braille.

En Resumen, las tecnologías accesibles que requieren acceso de solo lectura a un almacén de texto pueden usar <xref:System.Windows.Automation.TextPattern> , pero necesitarán la funcionalidad más compleja de TSF para la entrada compatible con el contexto.

<a name="Control_Types"></a>

## <a name="control-types"></a>Tipos de controles

### <a name="text"></a>Texto

El control de texto (Text) es el elemento básico que representa un fragmento de texto en la pantalla.

Un control de texto independiente puede usarse como una etiqueta o texto estático en un formulario. Los controles de texto también pueden estar dentro de la estructura de un <xref:System.Windows.Automation.ControlType.ListItem>, <xref:System.Windows.Automation.ControlType.TreeItem> o <xref:System.Windows.Automation.ControlType.DataItem>.

> [!NOTE]
> Es posible que los controles de texto no aparezcan en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (consulte [UI Automation Tree Overview](ui-automation-tree-overview.md)). Esto se debe a que los controles de texto se muestran a menudo a través de la propiedad Name de otro control. Por ejemplo, el texto que se usa para etiquetar un control de edición (Edit) se expone a través de la propiedad Name del control de edición. Dado que el control de edición que se encuentra en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , no es necesario que el elemento de texto esté en esa vista del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . El único texto que se muestra en la vista de contenido es el texto que no es información redundante. Esto permite a las tecnologías de asistencia filtrar rápidamente solo los fragmentos de información que necesitan los usuarios.

### <a name="edit"></a>Editar

Los controles de edición (Edit) permiten al usuario ver y editar una sola línea de texto.

> [!NOTE]
> La única línea de texto puede encapsularse en ciertos escenarios de diseño.

### <a name="document"></a>Documento

Los controles de documento permiten a un usuario navegar y obtener información de varias páginas de texto.

<a name="TextPattern_Client_API_s"></a>

## <a name="textpattern-client-apis"></a>API de cliente de TextPattern

|||
|-|-|
|`System.Windows.Automation.TextPattern Class`|Es el punto de entrada para el modelo de texto de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .<br /><br /> Esta clase también contiene las dos escuchas de eventos de <xref:System.Windows.Automation.TextPattern> , <xref:System.Windows.Automation.TextPattern.TextSelectionChangedEvent> y <xref:System.Windows.Automation.TextPattern.TextChangedEvent>.|
|`System.Windows.Automation.Text.TextPatternRange Class`|Es la representación de un intervalo de texto dentro de un contenedor de texto que admite <xref:System.Windows.Automation.TextPattern>.<br /><br /> Los clientes de automatización de la interfaz de usuario debe tener cuidado con la validez actual de un intervalo de texto creado con <xref:System.Windows.Automation.Text.TextPatternRange>. Si el texto original del control de texto se reemplaza totalmente por el nuevo texto, el intervalo de texto actual deja de ser válido. Sin embargo, puede que el intervalo de texto aún tenga alguna viabilidad si únicamente se cambia una parte del texto original y el control de texto subyacente está administrando su “puntero” de texto con delimitadores (o extremos) en lugar de con la posición de carácter absoluto.<br /><br /> Los clientes pueden realizar escuchas de un <xref:System.Windows.Automation.TextPattern.TextChangedEvent> para recibir notificaciones de los cambios realizados en el contenido textual con el que trabajan.|
|`System.Windows.Automation.AutomationTextAttribute Class`|Se usa para identificar los atributos de formato de un intervalo de texto.|

<a name="TextPattern_Provider_API_s"></a>

## <a name="textpattern-provider-apis"></a>API del proveedor TextPattern

Los controles o elementos de interfaz de usuario que admiten <xref:System.Windows.Automation.TextPattern> al implementar las interfaces <xref:System.Windows.Automation.Provider.ITextProvider> y <xref:System.Windows.Automation.Provider.ITextRangeProvider> , ya sea de forma nativa o mediante los proxy de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , son capaces de exponer información detallada de atributos sobre cualquier texto que contengan, además de proporcionar sólidas funcionalidades de navegación.

Un proveedor de <xref:System.Windows.Automation.TextPattern> no tiene que admitir todos los atributos de texto si el control no es compatible con algún atributo concreto.

Un proveedor de <xref:System.Windows.Automation.TextPattern> debe admitir las funciones <xref:System.Windows.Automation.TextPattern.GetSelection%2A> y <xref:System.Windows.Automation.Text.TextPatternRange.Select%2A> si el control admite la selección de texto o la ubicación del cursor de texto (o símbolo de inserción) dentro del área de texto. Si el control no admite esta funcionalidad, entonces no es necesario que admita ninguno de estos métodos. Sin embargo, el control debe implementar la propiedad <xref:System.Windows.Automation.Provider.ITextProvider.SupportedTextSelection%2A> a fin de exponer el tipo de selección de texto que admite.

Un proveedor de <xref:System.Windows.Automation.TextPattern> siempre debe admitir las constantes <xref:System.Windows.Automation.Text.TextUnit> y <xref:System.Windows.Automation.Text.TextUnit.Character> de <xref:System.Windows.Automation.Text.TextUnit.Document> , así como cualquier otras constantes de <xref:System.Windows.Automation.Text.TextUnit> que es capaz de admitir.

> [!NOTE]
> El proveedor puede omitir la compatibilidad para un determinado <xref:System.Windows.Automation.Text.TextUnit> si se aplaza al siguiente mayor <xref:System.Windows.Automation.Text.TextUnit> compatible en el orden siguiente: <xref:System.Windows.Automation.Text.TextUnit.Character>, <xref:System.Windows.Automation.Text.TextUnit.Format>, <xref:System.Windows.Automation.Text.TextUnit.Word>, <xref:System.Windows.Automation.Text.TextUnit.Line>, <xref:System.Windows.Automation.Text.TextUnit.Paragraph>, <xref:System.Windows.Automation.Text.TextUnit.Page>y <xref:System.Windows.Automation.Text.TextUnit.Document>.

|||
|-|-|
|`ITextProvider Interface`|Expone métodos, propiedades y los atributos que admiten <xref:System.Windows.Automation.TextPattern> en las aplicaciones cliente (consulte <xref:System.Windows.Automation.Provider.ITextProvider>).|
|`ITextRangeProvider Interface`|Representa un intervalo de texto en un proveedor de texto (consulte <xref:System.Windows.Automation.Provider.ITextRangeProvider>).|
|`System.Windows.Automation.TextPatternIdentifiers Class`|Contiene valores que se usan como identificadores para los proveedores de texto (consulte <xref:System.Windows.Automation.TextPatternIdentifiers>).|

<a name="Security"></a>

## <a name="security"></a>Seguridad

Las clase [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se diseñó teniendo en cuenta la seguridad (consulte [UI Automation Security Overview](ui-automation-security-overview.md)). Sin embargo, las clases TextPattern descritas en este artículo requieren algunas consideraciones de seguridad específicas.

- Los proveedores de texto de[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] proporcionan interfaces de solo lectura y no proporcionan la capacidad de cambiar el texto existente en un control.

- Los clientes de la automatización de la interfaz de usuario solo pueden usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] si son de plena "confianza". Un ejemplo de esto sería el escritorio de inicio de sesión protegido, donde tan solo pueden ejecutarse aplicaciones conocidas y de confianza.

- Los desarrolladores de proveedores de automatización de la interfaz de usuario deben tener en cuenta que toda la información que elijan exponer en sus controles a través de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] es básicamente pública y totalmente accesible por otro código. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] no realiza ningún esfuerzo para determinar la confiabilidad de cualquier cliente de automatización de la interfaz de usuario y, por tanto, el proveedor de automatización de la interfaz de usuario no debe exponer información textual confidencial o contenido protegido (por ejemplo, los campos de contraseña).

- Uno de los cambios más importantes en la seguridad de Windows Vista se denomina ampliamente "entrada segura", que abarca tecnologías como cuentas de usuario con privilegios mínimos (o limitados) y aislamiento de nivel de privilegios de interfaz de usuario (UIPI).

  - UIPI evita que un programa controle o supervise otro programa “con más privilegios”, lo que impide los ataques de mensajes de ventanas entre procesos que suplantan la entrada de los usuarios.

  - LUA establece límites en los privilegios de las aplicaciones ejecutadas por los usuarios del grupo Administradores. Las aplicaciones no tienen necesariamente privilegios de administrador, sino que en su lugar se ejecutarán con los privilegios mínimos necesarios. Como consecuencia, puede haber algunas restricciones que se apliquen en escenarios LUA. En particular, el truncamiento de cadenas (incluidas cadenas TextPattern), donde puede ser necesario limitar el tamaño de las cadenas que se recuperan desde las aplicaciones de nivel de administrador, de modo que no se vean obligadas a asignar memoria hasta el punto de deshabilitar la aplicación.

<a name="Performance"></a>

## <a name="performance"></a>Rendimiento

Dado la mayor parte de la funcionalidad de TextPattern se basa en las llamadas entre procesos, no proporciona un mecanismo de almacenamiento en caché para mejorar el rendimiento al procesar el contenido. Esto es diferente a otros patrones de control de la [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a los que se puede tener acceso mediante los métodos <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> .

Una táctica para mejorar el rendimiento es asegurarse de que los clientes de automatización de la interfaz de usuario intentan recuperar bloques de texto de tamaño moderado con <xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>. Por ejemplo, las llamadas a GetText(1) incurrirán en varios resultados entre procesos para cada carácter, mientras que una llamada a GetText (-1) incurrirá en un solo resultado entre procesos, pero puede tener una latencia elevada según el tamaño del proveedor de texto.

<a name="Glossary"></a>

## <a name="textpattern-terminology"></a>Terminología de TextPattern

**Atribui**\
Es una característica de formato de un intervalo de texto (por ejemplo, <xref:System.Windows.Automation.TextPattern.IsItalicAttribute> o <xref:System.Windows.Automation.TextPattern.FontNameAttribute>).

**Intervalo degenerado**\
Un intervalo degenerado es un intervalo de texto vacío o con cero caracteres. Para los fines del patrón de control TextPattern, el punto de inserción de texto (o símbolo de inserción) se considera un intervalo degenerado. Si no hay texto seleccionado, <xref:System.Windows.Automation.TextPattern.GetSelection%2A> devolverá un intervalo degenerado en el punto de inserción de texto y <xref:System.Windows.Automation.TextPattern.RangeFromPoint%2A> devolverá un intervalo degenerado como extremo inicial. <xref:System.Windows.Automation.TextPattern.RangeFromChild%2A> y <xref:System.Windows.Automation.TextPattern.GetVisibleRanges%2A> pueden devolver intervalos degenerados cuando el proveedor de texto no encuentra ningún intervalo de texto que coincida con la condición especificada. Este intervalo degenerado puede usarse como extremo inicial dentro del proveedor de texto. <xref:System.Windows.Automation.Text.TextPatternRange.FindText%2A>y <xref:System.Windows.Automation.Text.TextPatternRange.FindAttribute%2A> devuelven una referencia nula ( `Nothing` en Microsoft Visual Basic .net) para evitar la confusión con un intervalo descubierto en lugar de un intervalo degenerado.

**Objeto incrustado**\
Hay dos tipos de objetos incrustados en el modelo de texto de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que están formados por elementos de contenido basado en texto, como hipervínculos o tablas, y elementos de control, como imágenes y botones. Para información detallada, vea [Access Embedded Objects Using UI Automation](access-embedded-objects-using-ui-automation.md).

**Finales**\
Es el punto <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> o <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> absoluto de un intervalo de texto dentro de un contenedor de texto.

![TextPatternRangeEndpoints &#40;&#41; de inicio y finalización.](./media/uia-textpattern-endpoints.PNG "UIA_TextPattern_Endpoints")
En el siguiente ejemplo se muestra un conjunto de puntos de inicio y final.

**TextRange**\
Es una representación de un intervalo de texto, con puntos de inicio y final, en un contenedor de texto que incluye todos los atributos y la funcionalidad asociados.

<xref:System.Windows.Automation.Text.TextUnit>\
Unidad predefinida de texto (carácter, palabra, línea o párrafo) usada para navegar por los segmentos lógicos de un intervalo de texto.

## <a name="see-also"></a>Consulte también

- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Asignación de patrones de controles para clientes de UI Automation](control-pattern-mapping-for-ui-automation-clients.md)
- [Text Services Framework (TSF)](/windows/desktop/api/_tsf/)
