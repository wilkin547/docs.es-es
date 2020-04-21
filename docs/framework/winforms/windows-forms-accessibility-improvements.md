---
title: Mejoras en la accesibilidad de Windows Forms
description: Obtenga información sobre las formas en que los formularios Windows Forms de .NET Core intentan mejorar la accesibilidad en comparación con los formularios Windows Forms de .NET Framework.
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739767"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>Mejoras de accesibilidad en los controles de formularios Windows Forms para .NET Core 3.0

Windows Forms sigue mejorando la forma en que funciona con las tecnologías de accesibilidad para dar mejor soporte a los clientes de Windows Forms. Estas mejoras incluyen los cambios siguientes:

- Cambios en varias áreas de interacción con aplicaciones cliente de accesibilidad, incluido Narrador.
- Cambios en la jerarquía Accesible (mejorando la navegación a través del árbol de automatización de la interfaz de usuario).
- Cambios en la navegación por teclado.

> [!IMPORTANT]
> Los cambios de accesibilidad realizados en .NET Framework 4.7.1 a través de .NET Framework 4.8 se incluyen en .NET Core 3.0 y versiones posteriores y están habilitados de forma predeterminada. Los modificadores de compatibilidad compatibles con .NET Framework compatibles que permitían a las aplicaciones excluirse del nuevo comportamiento de accesibilidad. Por otro lado, .NET Core no admite esta configuración y no permite que las aplicaciones opten por no tener el comportamiento de accesibilidad.
  
A partir de .NET Core 3.0, las aplicaciones de Windows Forms se benefician de todas las nuevas características de accesibilidad (introducidas en .NET Framework 4.7.1 - 4.8) sin configuración adicional.

## <a name="listbox-accessibility-support"></a>Compatibilidad con ListBox Accessibility

Los siguientes cambios <xref:System.Windows.Forms.ListBox> se aplican al control:

- Compatibilidad habilitada de `ListBox` Automatización de la interfaz de usuarioUI Automation para el control.
- Compatibilidad `ListBox` de accesibilidad mejorada <xref:System.Windows.Automation.ScrollItemPattern> `ListBox` agregando los elementos y mejorando la generación y el control de eventos de accesibilidad y la navegación del Narrador a través de los elementos (la navegación de bloqueo de mayúsculas no es correcta y no lanza la navegación fuera del control involuntariamente).

## <a name="checkedlistbox-accessibility-support"></a>Compatibilidad con la accesibilidad de CheckedListBox

Los siguientes cambios <xref:System.Windows.Forms.CheckedListBox> se aplican al control:

- Corregidos `CheckedListBox` límites proporcionados por las propiedades de accesibilidad para las entradas.
- Mejora `ListBox` general `CheckedListBox` y accesibilidad: valores de propiedad corregidos y modelo de eventos.

## <a name="combobox-accessibility-support"></a>Compatibilidad con la accesibilidad de ComboBox

Los siguientes cambios <xref:System.Windows.Forms.ComboBox> se aplican al control:

- Se ha actualizado `ComboBox` el proceso de obtención de objetos de accesibilidad de elementos para habilitar la <xref:System.Object.GetHashCode%2A> generación de ida para los elementos en lugar de obtener códigos hash de los elementos, lo que puede no ser seguro en caso de que se invalide la función.

## <a name="datagridview-accessibility-support"></a>Compatibilidad con la accesibilidad de DataGridView

Los siguientes cambios <xref:System.Windows.Forms.DataGridView> se aplican al control:

- Corregido `DataGridView.Bounds` proporcionado por las propiedades de accesibilidad para columnas, filas, celdas y encabezados correspondientes, se mejoró el rendimiento del cálculo del rectángulo delimitador. Todos los límites de accesibilidad se representan correctamente teniendo en cuenta los límites de todo el control, junto con su ventana gráfica.
- Se `Value.IsReadOnly` ha corregido el valor de propiedad que proporciona aplicaciones cliente accesibles. La propiedad ahora `IsReadOnly` muestra el estado correcto para las celdas.
- Se ha <xref:System.Windows.Forms.DataGridView.CellParsing> corregido el problema con la generación de eventos para el primer cambio de celda. El valor de celda se puede `DataGridView` cambiar sin ningún problema, incluida la primera interacción de control.
- Se `DataGridView` ha mejorado el contraste de color de fondo al usar temas de contraste alto de Windows. Se `DataGridView` ha cambiado el color de retroceso predeterminado cuando se utilizan temas HC-1, HC-2 y HC Black.

## <a name="propertygrid-accessibility-support"></a>Compatibilidad con PropertyGrid Accessibility

Los siguientes cambios <xref:System.Windows.Forms.PropertyGrid> se aplican al control:

- Corregido `PropertyGrid.Bounds` proporcionado por las propiedades de accesibilidad para las entradas de cuadrícula, se ha mejorado el rendimiento del cálculo del rectángulo delimitador. Por ahora, todos los límites de accesibilidad se representan correctamente teniendo en cuenta los límites de todo el control, junto con su ventana gráfica.
- Se han corregido los nombres accesibles y las descripciones de los subcontroles para no incluir nombres de tipo de control y evitar el doble anuncio de nombres de tipo de control.

## <a name="toolstrip-accessibility-support"></a>Compatibilidad con la accesibilidad de ToolStrip

Los siguientes cambios <xref:System.Windows.Forms.ToolStrip> se aplican al control:

- Navegación mejorada `ToolStrip` `MenuStrip`a `StatusStrip` través de , , y elementos. Se `ToolStrip` `MenuStrip` ha corregido la navegación por mayúsculas y vueltas, recorriendo los elementos del menú cuando se presiona la flecha arriba de la pestaña de desplazamiento, que navega hasta el elemento de menú inferior.
- Navegación `MenuStrip` accesible mejorada, tipos de control accesibles de menú corregidos para submenús para crear submenús de tipo 'Menú' en lugar de 'MenuItem'.

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>Compatibilidad con printPreviewControl y PrintPreviewDialog Accesibilidad

Los siguientes cambios se aplican a los controles de impresión:

- Navegación accesible mejorada (incluida la navegación del Narrador) a través de elementos de menú.
- Los temas de alto contraste mejorados admiten e hicieron que el elemento de control se contraste más.

## <a name="stringcollectioneditor-accessibility-support"></a>Compatibilidad con la accesibilidad StringCollectionEditor

El diseñador de Windows Forms ahora usa el editor de colecciones de cadenas con compatibilidad de accesibilidad mejorada.

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>Compatibilidad con la accesibilidad de MonthCalendar (disponible en .NET Core 3.1)

Los siguientes cambios <xref:System.Windows.Forms.MonthCalendar> se aplican al control:

- Se agregaron proveedores de servidores automatización de la interfaz de usuario para `MonthCalendar` controlar, se agregaron el patrón de cuadrícula de automatización de la interfaz de usuario y los proveedores de patrones de tabla.
- Se ha cambiado el tipo de control accesible de _tabla_ al tipo de `MonthCalendar` control accesible de _calendario_ excepto `MonthCalendar` en el caso en que el control tiene un control de etiqueta anterior que define el nombre accesible del control, en este caso específico el tipo de control accesible se convierte en _tabla._
- Se ha mejorado `MonthCalendar` el anuncio de la fecha seleccionada para el control.
- Compatibilidad `MonthCalendar` de control mejorada para lectores de pantalla y otras herramientas de accesibilidad. En este momento, los usuarios pueden navegar por los elementos de control e interactuar con estos elementos mediante la entrada de solo teclado. Con Narrador, utilice CAPS + teclas de flecha para navegar por los elementos de control y CAPS + Intro para invocar la acción predeterminada del elemento.
- Se ha mejorado `MonthCalendar` la navegación con teclas de flecha a través de elementos secundarios con un rectángulo de enfoque: rectángulo de enfoque azul para Narrador.
- Mejora de la accesibilidad `MonthCalendar` para la acción `MonthCalendar` de prueba de posicionamiento para los elementos de control para permitir obtener elementos accesibles secundarios mediante coordenadas proporcionadas.

## <a name="tooltips-accessibility-available-in-net-core-31"></a>Accesibilidad sobre herramientas (disponible en .NET Core 3.1)

- Se ha añadido la capacidad de anunciar un texto de información sobre herramientas por aplicaciones de lector de pantalla como NVDA y Narrador. La aplicación de lector de pantalla ahora puede anunciar el texto de la información sobre herramientas del teclado o del mouse de cualquier control de formularios Windows Forms que esté configurado para mostrar información sobre herramientas.

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>Compatibilidad con la automatización de la interfaz de usuario para DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip y otros controles

La compatibilidad con Automatización de la interfaz de usuarioUI Automation está habilitada para los controles en tiempo de ejecución, pero no se usa durante el tiempo de diseño. Para obtener información general de la automatización de la interfaz de usuario, vea la [información general sobre la Automatización de la interfaz de usuario](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).

## <a name="see-also"></a>Consulte también

- [Prácticas recomendadas](../ui-automation/accessibility-best-practices.md)de accesibilidad .
