---
title: DatePicker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd2a1755ae076369661b2c9a7a2b744961cdb129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="datepicker"></a>DatePicker
El <xref:System.Windows.Controls.DatePicker> control permite al usuario seleccionar una fecha escribiéndola en un campo de texto o mediante el uso de una lista desplegable <xref:System.Windows.Controls.Calendar> control.  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.DatePicker>.  
  
 ![Control DatePicker](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")  
Control DatePicker  
  
 Cantidad de un <xref:System.Windows.Controls.DatePicker> son propiedades del control para administrar su integrado <xref:System.Windows.Controls.Calendar>y la función de forma idéntica a la propiedad equivalente en <xref:System.Windows.Controls.Calendar>. En concreto, el <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, y <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> propiedades funcionan de forma idéntica a sus <xref:System.Windows.Controls.Calendar> equivalentes. Para obtener más información, consulta <xref:System.Windows.Controls.Calendar>.  
  
 Los usuarios pueden escribir una fecha directamente en un campo de texto, que establece el <xref:System.Windows.Controls.DatePicker.Text%2A> propiedad. Si el <xref:System.Windows.Controls.DatePicker> no se puede convertir la cadena especificada en una fecha válida, el <xref:System.Windows.Controls.DatePicker.DateValidationError> se generará el evento. De forma predeterminada, esto produce una excepción, pero un controlador de eventos para <xref:System.Windows.Controls.DatePicker.DateValidationError> puede establecer el <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> propiedad `false` y evitar una excepción que se produzca.  
  
## <a name="see-also"></a>Vea también  
 [Controles](../../../../docs/framework/wpf/controls/index.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
