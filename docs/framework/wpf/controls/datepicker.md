---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: a135188b2c573a578aa5b6be4910e6d02471aee1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362258"
---
# <a name="datepicker"></a>DatePicker
El <xref:System.Windows.Controls.DatePicker> control permite al usuario seleccionar una fecha escribiéndola en un campo de texto o mediante el uso de una lista desplegable <xref:System.Windows.Controls.Calendar> control.  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.DatePicker>.  
  
 ![Control DatePicker](./media/ndp-datepicker.png "NDP_DatePicker")  
Control DatePicker  
  
 Muchos de un <xref:System.Windows.Controls.DatePicker> son propiedades del control para administrar su integrado <xref:System.Windows.Controls.Calendar>y la función de forma idéntica a la propiedad equivalente en <xref:System.Windows.Controls.Calendar>. En concreto, el <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, y <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> propiedades funcionan de forma idéntica a su <xref:System.Windows.Controls.Calendar> equivalentes. Para obtener más información, consulta <xref:System.Windows.Controls.Calendar>.  
  
 Los usuarios pueden escribir una fecha directamente en un campo de texto, que establece el <xref:System.Windows.Controls.DatePicker.Text%2A> propiedad. Si el <xref:System.Windows.Controls.DatePicker> no se puede convertir la cadena especificada en una fecha válida, el <xref:System.Windows.Controls.DatePicker.DateValidationError> , se generará el evento. De forma predeterminada, esto produce una excepción, pero un controlador de eventos <xref:System.Windows.Controls.DatePicker.DateValidationError> puede establecer el <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> propiedad `false` y evitar que se produzca una excepción.  
  
## <a name="see-also"></a>Vea también
- [Controles](index.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
