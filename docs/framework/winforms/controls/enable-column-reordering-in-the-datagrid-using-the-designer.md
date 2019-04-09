---
title: Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 966ffe131d10b97fe9632bb1ff23273b1dabd061
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194973"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="2c7a5-102">Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="2c7a5-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="2c7a5-103">Al ver los datos mostrados en un formulario Windows Forms <xref:System.Windows.Forms.DataGridView> control, los usuarios a veces desean comparar los valores en columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="2c7a5-104">Esto puede ser conveniente si las columnas están separadas en el control, especialmente si los usuarios deben desplazar horizontalmente con el fin de ver todas las columnas que están interesados.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="2c7a5-105">Puede realizar la tarea de comparar los valores de columna sea más fácil por permite a los usuarios reordenar las columnas.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="2c7a5-106">Cuando se habilita la reordenación de columnas, los usuarios pueden mover una columna a una nueva posición arrastrando el encabezado de columna con el mouse.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>  
  
 <span data-ttu-id="2c7a5-107">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2c7a5-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="2c7a5-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c7a5-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2c7a5-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="2c7a5-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2c7a5-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="2c7a5-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-enable-column-reordering"></a><span data-ttu-id="2c7a5-112">Para habilitar la reordenación de columnas</span><span class="sxs-lookup"><span data-stu-id="2c7a5-112">To enable column reordering</span></span>  
  
-   <span data-ttu-id="2c7a5-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Habilitar reordenación de columnas**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c7a5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c7a5-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2c7a5-115">Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="2c7a5-115">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="2c7a5-116">Filtrar Cree un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c7a5-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="2c7a5-117">Filtrar para agregar controles a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c7a5-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
