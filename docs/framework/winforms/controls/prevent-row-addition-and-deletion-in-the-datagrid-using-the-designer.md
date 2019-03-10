---
title: Procedimiento Impedir la adición de fila y eliminación en el Control de DataGridView de Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: 52514c07313a60bac8e2c7142b66099dbcd779e5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714745"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="bc8dd-102">Filtrar Impedir la adición de fila y eliminación en el Control de DataGridView de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="bc8dd-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="bc8dd-103">En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bc8dd-104">Las nuevas filas se escriben en la fila especial para los nuevos registros en la parte inferior del control.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="bc8dd-105">Al deshabilitar la adición de la fila, no se muestra la fila para los nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="bc8dd-106">A continuación, puede que el control sea de sólo lectura deshabilitando la eliminación de fila y la edición de celdas.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="bc8dd-107">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bc8dd-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bc8dd-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc8dd-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bc8dd-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="bc8dd-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bc8dd-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="bc8dd-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="bc8dd-112">Para evitar la eliminación y adición de fila</span><span class="sxs-lookup"><span data-stu-id="bc8dd-112">To prevent row addition and deletion</span></span>  
  
-   <span data-ttu-id="bc8dd-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> controlar y, a continuación, desactive la **Habilitar acción de agregar** y **Habilitar eliminación** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc8dd-114">Para que el control sea de solo lectura, desactive la **Habilitar edición** también la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="bc8dd-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8dd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc8dd-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bc8dd-116">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc8dd-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="bc8dd-117">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc8dd-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
