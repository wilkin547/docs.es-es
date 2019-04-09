---
title: Filtrar para mostrar la hora con el control DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: 5163ca3eb04732152960c86c9a7428d87c6280f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083044"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="c01dd-102">Filtrar para mostrar la hora con el control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="c01dd-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="c01dd-103">Si quiere la aplicación para permitir a los usuarios seleccionar una fecha y hora, y mostrar esa fecha y hora en el formato especificado, utilice el control <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="c01dd-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="c01dd-104">El siguiente procedimiento muestra cómo utilizar el control <xref:System.Windows.Forms.DateTimePicker> para mostrar la hora.</span><span class="sxs-lookup"><span data-stu-id="c01dd-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="c01dd-105">Para mostrar la hora con el control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="c01dd-105">To display the time with the DateTimePicker control</span></span>  
  
1.  <span data-ttu-id="c01dd-106">Establecer el <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad</span><span class="sxs-lookup"><span data-stu-id="c01dd-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to</span></span> <xref:System.Windows.Forms.DateTimePickerFormat.Time>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="c01dd-107">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> para el elemento <xref:System.Windows.Forms.DateTimePicker> en `true`.</span><span class="sxs-lookup"><span data-stu-id="c01dd-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="c01dd-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c01dd-108">Example</span></span>  
 <span data-ttu-id="c01dd-109">El ejemplo de código siguiente muestra cómo crear un <xref:System.Windows.Forms.DateTimePicker> que permita a los usuarios elegir solo una vez.</span><span class="sxs-lookup"><span data-stu-id="c01dd-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c01dd-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c01dd-110">Compiling the Code</span></span>  
 <span data-ttu-id="c01dd-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c01dd-111">This example requires:</span></span>  
  
-   <span data-ttu-id="c01dd-112">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="c01dd-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c01dd-113">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c01dd-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c01dd-114">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="c01dd-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01dd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c01dd-115">See also</span></span>

- [<span data-ttu-id="c01dd-116">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="c01dd-116">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
