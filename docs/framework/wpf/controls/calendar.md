---
title: "Calendar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Calendar (control) [WPF]"
  - "controles [WPF], Calendar"
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Calendar
Un calendario permite a un usuario seleccionar una fecha mediante una presentación visual del calendario.  
  
 Un control <xref:System.Windows.Controls.Calendar> se puede utilizar solo o como una parte desplegable de un control <xref:System.Windows.Controls.DatePicker>.  Para obtener más información, vea <xref:System.Windows.Controls.DatePicker>.  
  
 En la siguiente ilustración se muestran dos controles <xref:System.Windows.Controls.Calendar>, uno con selecciones y fechas no disponibles y otro sin ellas.  
  
 ![Controles de calendario](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP\_CalendarControls")  
Controles Calendar  
  
 En la siguiente tabla se proporciona información sobre las tareas que están asociadas normalmente a <xref:System.Windows.Controls.Calendar>.  
  
|Tarea|Implementación|  
|-----------|--------------------|  
|Especificar fechas que no se pueden seleccionar.|Utilizar la propiedad <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|Hacer que <xref:System.Windows.Controls.Calendar> muestre un mes, un año completo o una década.|Establecer la propiedad <xref:System.Windows.Controls.Calendar.DisplayMode%2A> en Mes, Año o Década.|  
|Especificar si el usuario puede seleccionar una fecha, un intervalo de fechas o varios intervalos de fechas.|Utilizar <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Especificar el intervalo de fechas que muestra <xref:System.Windows.Controls.Calendar>.|Utilice las propiedades <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> y <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>.|  
|Especificar si se resalta la fecha actual.|Utilizar la propiedad <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>.  De manera predeterminada, <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> es `true`.|  
|Cambiar el tamaño de <xref:System.Windows.Controls.Calendar>.|Usar <xref:System.Windows.Controls.Viewbox> o establecer la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> en <xref:System.Windows.Media.ScaleTransform>.  Observe que, si establece las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.Calendar>, el calendario real no cambia su tamaño.|  
  
 El control <xref:System.Windows.Controls.Calendar> proporciona navegación básica mediante el mouse o el teclado.  En la tabla siguiente se resume la navegación con el teclado.  
  
|Combinación de teclas|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Acción|  
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|FLECHA|<xref:System.Windows.Controls.CalendarMode>|Cambia la propiedad <xref:System.Windows.Controls.Calendar.SelectedDate%2A> si la propiedad <xref:System.Windows.Controls.Calendar.SelectionMode%2A> no se establece en <xref:System.Windows.Controls.CalendarSelectionMode>.|  
|FLECHA|<xref:System.Windows.Controls.CalendarMode>|Cambia el mes de la propiedad <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.  Observe que <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|FLECHA|<xref:System.Windows.Controls.CalendarMode>|Cambia el año de <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.  Observe que <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|MAYÚS\+FLECHA|<xref:System.Windows.Controls.CalendarMode>|Si <xref:System.Windows.Controls.Calendar.SelectionMode%2A> no está establecido en <xref:System.Windows.Controls.CalendarSelectionMode> o <xref:System.Windows.Controls.CalendarSelectionMode>, amplía el intervalo de las fechas seleccionadas.|  
|INICIO|<xref:System.Windows.Controls.CalendarMode>|Cambia <xref:System.Windows.Controls.Calendar.SelectedDate%2A> al primer día del mes en curso.|  
|INICIO|<xref:System.Windows.Controls.CalendarMode>|Cambia el mes de <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primer mes del año.  El valor de la propiedad <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|INICIO|<xref:System.Windows.Controls.CalendarMode>|Cambia el año de <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primer año de la década.  El valor de la propiedad <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|FIN|<xref:System.Windows.Controls.CalendarMode>|Cambia <xref:System.Windows.Controls.Calendar.SelectedDate%2A> al último día del mes en curso.|  
|FIN|<xref:System.Windows.Controls.CalendarMode>|Cambia el mes de <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al último mes del año.  El valor de la propiedad <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|FIN|<xref:System.Windows.Controls.CalendarMode>|Cambia el año de <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al último año de la década.  El valor de la propiedad <xref:System.Windows.Controls.Calendar.SelectedDate%2A> no cambia.|  
|CTRL\+FLECHA ARRIBA|Cualquiera|Cambia al siguiente <xref:System.Windows.Controls.Calendar.DisplayMode%2A> mayor.  Si <xref:System.Windows.Controls.Calendar.DisplayMode%2A> ya es <xref:System.Windows.Controls.CalendarMode>, no se realiza ninguna acción.|  
|CTRL\+FLECHA ABAJO|Cualquiera|Cambia al siguiente <xref:System.Windows.Controls.Calendar.DisplayMode%2A> menor.  Si <xref:System.Windows.Controls.Calendar.DisplayMode%2A> ya es <xref:System.Windows.Controls.CalendarMode>, no se realiza ninguna acción.|  
|BARRA ESPACIADORA o ENTRAR|<xref:System.Windows.Controls.CalendarMode> o <xref:System.Windows.Controls.CalendarMode>|Cambia <xref:System.Windows.Controls.Calendar.DisplayMode%2A> a <xref:System.Windows.Controls.CalendarMode> o <xref:System.Windows.Controls.CalendarMode> representado por el elemento con el foco.|  
  
## Vea también  
 [Controles](../../../../docs/framework/wpf/controls/index.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)