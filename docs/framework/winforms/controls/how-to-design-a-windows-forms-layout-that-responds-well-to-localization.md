---
title: Filtrar para crear un diseño de formularios Windows Forms que sea apropiado para la localización
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
ms.openlocfilehash: 095427ce633ee6db5a448c8f3f69304ed25ab82a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142602"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="83508-102">Filtrar para crear un diseño de formularios Windows Forms que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="83508-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="83508-103">La creación de formularios ya listos para ser localizados acelera en gran medida el desarrollo para los mercados internacionales.</span><span class="sxs-lookup"><span data-stu-id="83508-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="83508-104">Puede utilizar el control <xref:System.Windows.Forms.TableLayoutPanel> para implementar diseños que respondan correctamente cuando los controles cambien de tamaño debido a los cambios en los valores de la propiedad <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="83508-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83508-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83508-105">Example</span></span>  
 <span data-ttu-id="83508-106">Este formulario muestra cómo crear un diseño que se ajusta proporcionalmente cuando traduce los valores de cadena mostrados a otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="83508-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="83508-107">Este proceso de traducción se denomina *localización*.</span><span class="sxs-lookup"><span data-stu-id="83508-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="83508-108">Para más información, consulte [Localización](../../../standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="83508-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="83508-109">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="83508-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="83508-110">Vea también [Tutorial: Crear un diseño que ajuste las proporciones para la localización](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="83508-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="83508-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="83508-111">Additional resources</span></span>
1.  [<span data-ttu-id="83508-112">Filtrar para alinear y expandir un control en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="83508-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [<span data-ttu-id="83508-113">Tutorial: Organizar controles en formularios Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="83508-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3.  [<span data-ttu-id="83508-114">Filtrar para abarcar filas y columnas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="83508-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [<span data-ttu-id="83508-115">Filtrar para editar columnas y filas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="83508-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  [<span data-ttu-id="83508-116">Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83508-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6.  [<span data-ttu-id="83508-117">Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="83508-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7.  [<span data-ttu-id="83508-118">Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="83508-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8.  [<span data-ttu-id="83508-119">Filtrar Admitir la localización en formularios de Windows Forms mediante AutoSize y el Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="83508-119">How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [<span data-ttu-id="83508-120">Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos</span><span class="sxs-lookup"><span data-stu-id="83508-120">Walkthrough: Creating a Resizable Windows Form for Data Entry</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83508-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="83508-121">Compiling the Code</span></span>  
 <span data-ttu-id="83508-122">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="83508-122">This example requires:</span></span>  
  
-   <span data-ttu-id="83508-123">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="83508-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="83508-124">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="83508-124">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="83508-125">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="83508-125">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83508-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="83508-126">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="83508-127">Localización</span><span class="sxs-lookup"><span data-stu-id="83508-127">Localization</span></span>](../../../standard/globalization-localization/localization.md)
