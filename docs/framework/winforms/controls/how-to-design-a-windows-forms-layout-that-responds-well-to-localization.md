---
title: Procedimiento Crear un diseño de formularios de Windows que sea apropiado para la localización
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 15f290f7d076eede7a8092d7295df810e4e51bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563527"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="9f65d-102">Procedimiento Crear un diseño de formularios de Windows que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="9f65d-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="9f65d-103">La creación de formularios ya listos para ser localizados acelera en gran medida el desarrollo para los mercados internacionales.</span><span class="sxs-lookup"><span data-stu-id="9f65d-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="9f65d-104">Puede utilizar el control <xref:System.Windows.Forms.TableLayoutPanel> para implementar diseños que respondan correctamente cuando los controles cambien de tamaño debido a los cambios en los valores de la propiedad <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f65d-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f65d-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f65d-105">Example</span></span>  
 <span data-ttu-id="9f65d-106">Este formulario muestra cómo crear un diseño que se ajusta proporcionalmente cuando traduce los valores de cadena mostrados a otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="9f65d-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="9f65d-107">Este proceso de traducción se denomina *localización*.</span><span class="sxs-lookup"><span data-stu-id="9f65d-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="9f65d-108">Para más información, consulte [Localización](../../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="9f65d-108">For more information, see [Localization](../../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="9f65d-109">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="9f65d-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="9f65d-110">Vea también [Tutorial: Crear un diseño que ajuste las proporciones para la localización](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9f65d-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [<span data-ttu-id="9f65d-111">Cómo: Alinear y expandir un Control en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9f65d-111">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  <span data-ttu-id="9f65d-112">[Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f65d-112">[Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span></span>  
  
3.  [<span data-ttu-id="9f65d-113">Cómo: Abarcar filas y columnas en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9f65d-113">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [<span data-ttu-id="9f65d-114">Cómo: Editar columnas y filas en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9f65d-114">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  <span data-ttu-id="9f65d-115">[Tutorial: Realizar tareas comunes mediante Smart etiquetas en Windows Forms controles](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f65d-115">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span></span>  
  
6.  <span data-ttu-id="9f65d-116">[Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f65d-116">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
7.  <span data-ttu-id="9f65d-117">[Tutorial: Diseñar Windows controles Forms con relleno, márgenes y la propiedad AutoSize](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f65d-117">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span></span>  
  
8.  <span data-ttu-id="9f65d-118">[Cómo: Admitir la localización en formularios de Windows Forms mediante AutoSize y el Control TableLayoutPanel](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f65d-118">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span></span>  
  
9. <span data-ttu-id="9f65d-119">[Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f65d-119">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f65d-120">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9f65d-120">Compiling the Code</span></span>  
 <span data-ttu-id="9f65d-121">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9f65d-121">This example requires:</span></span>  
  
-   <span data-ttu-id="9f65d-122">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9f65d-122">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9f65d-123">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9f65d-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9f65d-124">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9f65d-124">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9f65d-125">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9f65d-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f65d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f65d-126">See also</span></span>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="9f65d-127">Localización</span><span class="sxs-lookup"><span data-stu-id="9f65d-127">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)
