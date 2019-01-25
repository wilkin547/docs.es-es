---
title: Procedimiento Crear un formulario de Windows puede cambiar el tamaño de entrada de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: a632b243715ee42243c184aa2aca25abb6347f9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733329"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="316ce-102">Procedimiento Crear un formulario de Windows puede cambiar el tamaño de entrada de datos</span><span class="sxs-lookup"><span data-stu-id="316ce-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="316ce-103">Un buen diseño responde bien a los cambios en las dimensiones de su formulario principal.</span><span class="sxs-lookup"><span data-stu-id="316ce-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="316ce-104">Puede usar el control <xref:System.Windows.Forms.TableLayoutPanel> para organizar el diseño del formulario de manera que el tamaño y la posición de los controles cambien de una manera coherente cuando cambien las dimensiones del formulario.</span><span class="sxs-lookup"><span data-stu-id="316ce-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="316ce-105">El control <xref:System.Windows.Forms.TableLayoutPanel> también es útil cuando los cambios en el contenido de los controles producen cambios en el diseño.</span><span class="sxs-lookup"><span data-stu-id="316ce-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="316ce-106">El proceso descrito en este procedimiento puede realizarse en el entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="316ce-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="316ce-107">Consulte también [Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos](https://msdn.microsoft.com/library/991eahec\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="316ce-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://msdn.microsoft.com/library/991eahec\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="316ce-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="316ce-108">Example</span></span>  
 <span data-ttu-id="316ce-109">En el ejemplo siguiente se muestra cómo usar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un diseño que responda bien cuando el usuario cambie el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="316ce-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="316ce-110">También se muestra un diseño que responde bien a la localización.</span><span class="sxs-lookup"><span data-stu-id="316ce-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="316ce-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="316ce-111">Compiling the Code</span></span>  
 <span data-ttu-id="316ce-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="316ce-112">This example requires:</span></span>  
  
-   <span data-ttu-id="316ce-113">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="316ce-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="316ce-114">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="316ce-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="316ce-115">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="316ce-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="316ce-116">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="316ce-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="316ce-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="316ce-117">See also</span></span>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="316ce-118">Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="316ce-118">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="316ce-119">Cómo: Crear un diseño de formularios de Windows que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="316ce-119">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="316ce-120">Experiencia de usuario de Microsoft Windows, Official Guidelines for diseñadores y desarrolladores de interfaz de usuario. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span><span class="sxs-lookup"><span data-stu-id="316ce-120">Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span></span>](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
