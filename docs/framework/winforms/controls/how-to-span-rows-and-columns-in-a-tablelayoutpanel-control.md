---
title: Procedimiento para abarcar filas y columnas en un control TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 02db78b07930676235e55e535fb24f6ff618d823
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339026"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="20632-102">Procedimiento para abarcar filas y columnas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="20632-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="20632-103">Los controles en un <xref:System.Windows.Forms.TableLayoutPanel> control puede abarcar filas y columnas adyacentes.</span><span class="sxs-lookup"><span data-stu-id="20632-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20632-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="20632-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="20632-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="20632-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="20632-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="20632-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="20632-107">Para abarcar filas y columnas</span><span class="sxs-lookup"><span data-stu-id="20632-107">To span columns and rows</span></span>  
  
1. <span data-ttu-id="20632-108">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="20632-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2. <span data-ttu-id="20632-109">Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en la celda superior izquierda de la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="20632-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3. <span data-ttu-id="20632-110">Establecer el <xref:System.Windows.Forms.Button> del control **ColumnSpan** propiedad **2**.</span><span class="sxs-lookup"><span data-stu-id="20632-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="20632-111">Tenga en cuenta que el <xref:System.Windows.Forms.Button> control abarca la primera y segunda columna.</span><span class="sxs-lookup"><span data-stu-id="20632-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4. <span data-ttu-id="20632-112">Establecer el <xref:System.Windows.Forms.Button> del control **RowSpan** propiedad **2**.</span><span class="sxs-lookup"><span data-stu-id="20632-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="20632-113">Tenga en cuenta que el <xref:System.Windows.Forms.Button> control abarca la primera y segunda fila.</span><span class="sxs-lookup"><span data-stu-id="20632-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5. <span data-ttu-id="20632-114">Establecer el <xref:System.Windows.Forms.Button> del control **ColumnSpan** propiedad **1**.</span><span class="sxs-lookup"><span data-stu-id="20632-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="20632-115">Tenga en cuenta que el <xref:System.Windows.Forms.Button> control pasa a la primera columna y abarca la primera y segunda fila.</span><span class="sxs-lookup"><span data-stu-id="20632-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20632-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="20632-116">See also</span></span>

- [<span data-ttu-id="20632-117">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="20632-117">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
