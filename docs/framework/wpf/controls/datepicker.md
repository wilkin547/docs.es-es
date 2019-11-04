---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460357"
---
# <a name="datepicker"></a>DatePicker
El control <xref:System.Windows.Controls.DatePicker> permite al usuario seleccionar una fecha escribiéndola en un campo de texto o mediante un control de lista desplegable <xref:System.Windows.Controls.Calendar>.  
  
 En la ilustración siguiente se muestra un <xref:System.Windows.Controls.DatePicker>.  
  
 ![Control DatePicker](./media/ndp-datepicker.png "NDP_DatePicker")  
Control DatePicker  
  
 Muchas de las propiedades de un control <xref:System.Windows.Controls.DatePicker> son para administrar su <xref:System.Windows.Controls.Calendar>integrado y funcionan de manera idéntica a la propiedad equivalente en <xref:System.Windows.Controls.Calendar>. En concreto, las propiedades <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>y <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> funcionan de manera idéntica a sus homólogos <xref:System.Windows.Controls.Calendar>. Para obtener más información, vea <xref:System.Windows.Controls.Calendar>.  
  
 Los usuarios pueden escribir una fecha directamente en un campo de texto, lo que establece la propiedad <xref:System.Windows.Controls.DatePicker.Text%2A>. Si el <xref:System.Windows.Controls.DatePicker> no puede convertir la cadena especificada en una fecha válida, se producirá el evento de <xref:System.Windows.Controls.DatePicker.DateValidationError>. De forma predeterminada, esto produce una excepción, pero un controlador de eventos para <xref:System.Windows.Controls.DatePicker.DateValidationError> puede establecer la propiedad <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> en `false` y evitar que se genere una excepción.  
  
## <a name="see-also"></a>Vea también

- [Controles](index.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
