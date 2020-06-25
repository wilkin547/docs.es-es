---
title: Procedimiento para mostrar la hora con el control DateTimePicker
description: Aprenda a usar el control Windows Forms DateTimePicker para permitir a los usuarios seleccionar una fecha y hora, y mostrar esa fecha y hora en el formato especificado.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: ab584367a189d05e567bb57d386c6bf629201102
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325589"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="fc3ba-103">Procedimiento para mostrar la hora con el control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="fc3ba-103">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="fc3ba-104">Si quiere la aplicación para permitir a los usuarios seleccionar una fecha y hora, y mostrar esa fecha y hora en el formato especificado, utilice el control <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-104">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="fc3ba-105">El siguiente procedimiento muestra cómo utilizar el control <xref:System.Windows.Forms.DateTimePicker> para mostrar la hora.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-105">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="fc3ba-106">Para mostrar la hora con el control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="fc3ba-106">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="fc3ba-107">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en <xref:System.Windows.Forms.DateTimePickerFormat.Time>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="fc3ba-108">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> para el elemento <xref:System.Windows.Forms.DateTimePicker> en `true`.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-108">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="fc3ba-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc3ba-109">Example</span></span>  
 <span data-ttu-id="fc3ba-110">El ejemplo de código siguiente muestra cómo crear un <xref:System.Windows.Forms.DateTimePicker> que permita a los usuarios elegir solo una vez.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-110">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc3ba-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fc3ba-111">Compiling the Code</span></span>  
 <span data-ttu-id="fc3ba-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fc3ba-112">This example requires:</span></span>  
  
- <span data-ttu-id="fc3ba-113">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3ba-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc3ba-114">See also</span></span>

- [<span data-ttu-id="fc3ba-115">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="fc3ba-115">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
