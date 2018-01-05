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
# <a name="datepicker"></a><span data-ttu-id="dd2db-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="dd2db-102">DatePicker</span></span>
<span data-ttu-id="dd2db-103">El <xref:System.Windows.Controls.DatePicker> control permite al usuario seleccionar una fecha escribiéndola en un campo de texto o mediante el uso de una lista desplegable <xref:System.Windows.Controls.Calendar> control.</span><span class="sxs-lookup"><span data-stu-id="dd2db-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="dd2db-104">La siguiente ilustración muestra un <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="dd2db-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="dd2db-105">![Control DatePicker](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="dd2db-105">![DatePicker control](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="dd2db-106">Control DatePicker</span><span class="sxs-lookup"><span data-stu-id="dd2db-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="dd2db-107">Cantidad de un <xref:System.Windows.Controls.DatePicker> son propiedades del control para administrar su integrado <xref:System.Windows.Controls.Calendar>y la función de forma idéntica a la propiedad equivalente en <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="dd2db-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="dd2db-108">En concreto, el <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, y <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> propiedades funcionan de forma idéntica a sus <xref:System.Windows.Controls.Calendar> equivalentes.</span><span class="sxs-lookup"><span data-stu-id="dd2db-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="dd2db-109">Para obtener más información, consulta <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="dd2db-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="dd2db-110">Los usuarios pueden escribir una fecha directamente en un campo de texto, que establece el <xref:System.Windows.Controls.DatePicker.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="dd2db-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="dd2db-111">Si el <xref:System.Windows.Controls.DatePicker> no se puede convertir la cadena especificada en una fecha válida, el <xref:System.Windows.Controls.DatePicker.DateValidationError> se generará el evento.</span><span class="sxs-lookup"><span data-stu-id="dd2db-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="dd2db-112">De forma predeterminada, esto produce una excepción, pero un controlador de eventos para <xref:System.Windows.Controls.DatePicker.DateValidationError> puede establecer el <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> propiedad `false` y evitar una excepción que se produzca.</span><span class="sxs-lookup"><span data-stu-id="dd2db-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2db-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd2db-113">See Also</span></span>  
 [<span data-ttu-id="dd2db-114">Controles</span><span class="sxs-lookup"><span data-stu-id="dd2db-114">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="dd2db-115">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="dd2db-115">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
