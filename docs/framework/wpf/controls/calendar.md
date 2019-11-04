---
title: Calendario
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: e99a716e7ca8f7b2c9ed11543f37e0b8cb7422a6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460807"
---
# <a name="calendar"></a>Calendario
Un calendario permite a un usuario seleccionar una fecha mediante una presentación del calendario visual.  
  
 Un control <xref:System.Windows.Controls.Calendar> se puede usar por sí solo o como parte desplegable de un control <xref:System.Windows.Controls.DatePicker>. Para obtener más información, vea <xref:System.Windows.Controls.DatePicker>.  
  
 En la ilustración siguiente se muestran dos controles <xref:System.Windows.Controls.Calendar>, uno con selecciones y fechas no disponibilidad y otro sin.  
  
 ![Controles de calendario](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Controles de calendario  
  
 En la tabla siguiente se proporciona información sobre las tareas que se suelen asociar a la <xref:System.Windows.Controls.Calendar>.  
  
|Tarea|Implementación|  
|----------|--------------------|  
|Especifique fechas que no se pueden seleccionar.|Utilice la propiedad <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|Tenga el <xref:System.Windows.Controls.Calendar> mostrar un mes, todo un año o una década.|Establezca la propiedad <xref:System.Windows.Controls.Calendar.DisplayMode%2A> en month, Year o década.|  
|Especifique si el usuario puede seleccionar una fecha, un intervalo de fechas o varios intervalos de fechas.|Use el <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Especifique el intervalo de fechas que muestra el <xref:System.Windows.Controls.Calendar>.|Use las propiedades <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> y <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>.|  
|Especifique si la fecha actual se resalta.|Utilice la propiedad <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>. De forma predeterminada, <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> es `true`.|  
|Cambiar el tamaño de la <xref:System.Windows.Controls.Calendar>.|Use un <xref:System.Windows.Controls.Viewbox> o establezca la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> en un <xref:System.Windows.Media.ScaleTransform>. Tenga en cuenta que si establece las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de una <xref:System.Windows.Controls.Calendar>, el calendario real no cambia su tamaño.|  
  
 El control <xref:System.Windows.Controls.Calendar> proporciona una navegación básica mediante el mouse o el teclado. En la tabla siguiente se resume la navegación mediante el teclado.  
  
|Combinación de teclas|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Acción|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|SITUADA|<xref:System.Windows.Controls.CalendarMode.Month>|Cambia la propiedad <xref:System.Windows.Controls.Calendar.SelectedDate%2A> si la propiedad <xref:System.Windows.Controls.Calendar.SelectionMode%2A> no está establecida en <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|SITUADA|<xref:System.Windows.Controls.CalendarMode.Year>|Cambia el mes de la propiedad <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Tenga en cuenta que el <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|SITUADA|<xref:System.Windows.Controls.CalendarMode.Decade>|Cambia el año del <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Tenga en cuenta que el <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|Mayús + flecha|<xref:System.Windows.Controls.CalendarMode.Month>|Si <xref:System.Windows.Controls.Calendar.SelectionMode%2A> no se establece en <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> o <xref:System.Windows.Controls.CalendarSelectionMode.None>, extiende el intervalo de fechas seleccionadas.|  
|INICIO|<xref:System.Windows.Controls.CalendarMode.Month>|Cambia el <xref:System.Windows.Controls.Calendar.SelectedDate%2A> al primer día del mes actual.|  
|INICIO|<xref:System.Windows.Controls.CalendarMode.Year>|Cambia el mes del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primer mes del año. El <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|INICIO|<xref:System.Windows.Controls.CalendarMode.Decade>|Cambia el año del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primer año de la década. El <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|FIN|<xref:System.Windows.Controls.CalendarMode.Month>|Cambia el <xref:System.Windows.Controls.Calendar.SelectedDate%2A> al último día del mes actual.|  
|FIN|<xref:System.Windows.Controls.CalendarMode.Year>|Cambia el mes del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al último mes del año. El <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|FIN|<xref:System.Windows.Controls.CalendarMode.Decade>|Cambia el año del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al último año de la década. El <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|CTRL+FLECHA ARRIBA|Cualquiera|Cambia a la siguiente <xref:System.Windows.Controls.Calendar.DisplayMode%2A>mayor. Si <xref:System.Windows.Controls.Calendar.DisplayMode%2A> ya está <xref:System.Windows.Controls.CalendarMode.Decade>, no hay ninguna acción.|  
|CTRL+FLECHA ABAJO|Cualquiera|Cambia a la siguiente <xref:System.Windows.Controls.Calendar.DisplayMode%2A>más pequeña. Si <xref:System.Windows.Controls.Calendar.DisplayMode%2A> ya está <xref:System.Windows.Controls.CalendarMode.Month>, no hay ninguna acción.|  
|BARRA ESPACIAdora o entrar|<xref:System.Windows.Controls.CalendarMode.Year> o <xref:System.Windows.Controls.CalendarMode.Decade>|Cambia <xref:System.Windows.Controls.Calendar.DisplayMode%2A> al <xref:System.Windows.Controls.CalendarMode.Month> o <xref:System.Windows.Controls.CalendarMode.Year> representado por el elemento con el foco.|  
  
## <a name="see-also"></a>Vea también

- [Controles](index.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
