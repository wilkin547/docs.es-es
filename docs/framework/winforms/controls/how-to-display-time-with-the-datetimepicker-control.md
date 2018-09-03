---
title: 'Cómo: Mostrar la hora con el control DateTimePicker'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: c65a1102ccb8b05602d813831745dbcefed8c17d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484398"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="b51ef-102">Cómo: Mostrar la hora con el control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="b51ef-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="b51ef-103">Si quiere la aplicación para permitir a los usuarios seleccionar una fecha y hora, y mostrar esa fecha y hora en el formato especificado, utilice el control <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="b51ef-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="b51ef-104">El siguiente procedimiento muestra cómo utilizar el control <xref:System.Windows.Forms.DateTimePicker> para mostrar la hora.</span><span class="sxs-lookup"><span data-stu-id="b51ef-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="b51ef-105">Para mostrar la hora con el control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="b51ef-105">To display the time with the DateTimePicker control</span></span>  
  
1.  <span data-ttu-id="b51ef-106">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en <xref:System.Windows.Forms.DateTimePickerFormat.Time>.</span><span class="sxs-lookup"><span data-stu-id="b51ef-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="b51ef-107">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> para el elemento <xref:System.Windows.Forms.DateTimePicker> en `true`.</span><span class="sxs-lookup"><span data-stu-id="b51ef-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="b51ef-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b51ef-108">Example</span></span>  
 <span data-ttu-id="b51ef-109">El ejemplo de código siguiente muestra cómo crear un <xref:System.Windows.Forms.DateTimePicker> que permita a los usuarios elegir solo una vez.</span><span class="sxs-lookup"><span data-stu-id="b51ef-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b51ef-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b51ef-110">Compiling the Code</span></span>  
 <span data-ttu-id="b51ef-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b51ef-111">This example requires:</span></span>  
  
-   <span data-ttu-id="b51ef-112">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b51ef-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b51ef-113">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b51ef-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b51ef-114">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b51ef-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b51ef-115">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b51ef-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51ef-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b51ef-116">See Also</span></span>  
 [<span data-ttu-id="b51ef-117">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="b51ef-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)
