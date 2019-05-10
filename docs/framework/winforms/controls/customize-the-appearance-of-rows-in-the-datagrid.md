---
title: Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 32a21705b553ec915b4510dbe2fa32a0ae097d96
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648159"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fd4a3-102">Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd4a3-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fd4a3-103">Puede controlar la apariencia de las filas de <xref:System.Windows.Forms.DataGridView> controlando el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>, o ambos.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="fd4a3-104">Estos eventos están diseñados para que pueda representar solo lo que se desea mientras permite que el control <xref:System.Windows.Forms.DataGridView> represente el resto.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="fd4a3-105">Por ejemplo, si quiere representar un fondo personalizado, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> y dejar que las celdas individuales representen su propio contenido de primer plano.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="fd4a3-106">También tiene la opción de dejar que las celdas se representen a sí mismas y agregar contenido de primer plano personalizado en un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="fd4a3-107">Además, puede deshabilitar la representación de las celdas y representar todo usted mismo en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="fd4a3-108">En el ejemplo de código siguiente, se implementan controladores de ambos eventos para ofrecer un fondo de selección de degradado y algún contenido de primer plano personalizado que abarca varias columnas.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd4a3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd4a3-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd4a3-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fd4a3-110">Compiling the Code</span></span>  
 <span data-ttu-id="fd4a3-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fd4a3-111">This example requires:</span></span>  
  
- <span data-ttu-id="fd4a3-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fd4a3-113">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a3-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fd4a3-114">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="fd4a3-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fd4a3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd4a3-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="fd4a3-116">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd4a3-116">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fd4a3-117">Arquitectura del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="fd4a3-117">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
