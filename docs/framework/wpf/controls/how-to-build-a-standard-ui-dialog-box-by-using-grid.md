---
title: Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923414"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="5b1b1-102">Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid</span><span class="sxs-lookup"><span data-stu-id="5b1b1-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="5b1b1-103">En este ejemplo se muestra cómo crear un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] cuadro de diálogo estándar mediante <xref:System.Windows.Controls.Grid> el elemento.</span><span class="sxs-lookup"><span data-stu-id="5b1b1-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b1b1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b1b1-104">Example</span></span>  
 <span data-ttu-id="5b1b1-105">En el ejemplo siguiente se crea un cuadro de diálogo como el cuadro de diálogo **Ejecutar** en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="5b1b1-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="5b1b1-106">En el ejemplo se <xref:System.Windows.Controls.Grid> crea un y <xref:System.Windows.Controls.ColumnDefinition> se <xref:System.Windows.Controls.RowDefinition> usan las clases y para definir cinco columnas y cuatro filas.</span><span class="sxs-lookup"><span data-stu-id="5b1b1-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="5b1b1-107">A continuación, el ejemplo agrega y <xref:System.Windows.Controls.Image>coloca `RunIcon.png`un,, para representar la imagen que se encuentra en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5b1b1-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="5b1b1-108">La imagen se coloca en la primera columna y fila de <xref:System.Windows.Controls.Grid> (la esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="5b1b1-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="5b1b1-109">A continuación, el ejemplo agrega <xref:System.Windows.Controls.TextBlock> un elemento a la primera columna, que abarca las columnas restantes de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="5b1b1-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="5b1b1-110">Agrega otro <xref:System.Windows.Controls.TextBlock> elemento a la segunda fila de la primera columna para representar el cuadro de texto **abrir** .</span><span class="sxs-lookup"><span data-stu-id="5b1b1-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="5b1b1-111">A <xref:System.Windows.Controls.TextBlock> continuación, que representa el área de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="5b1b1-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="5b1b1-112">Por último, en el ejemplo <xref:System.Windows.Controls.Button> se agregan tres elementos a la fila final, que representan los eventos **OK**, **Cancel**y **Browse** .</span><span class="sxs-lookup"><span data-stu-id="5b1b1-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5b1b1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b1b1-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="5b1b1-114">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="5b1b1-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="5b1b1-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5b1b1-115">How-to Topics</span></span>](grid-how-to-topics.md)
