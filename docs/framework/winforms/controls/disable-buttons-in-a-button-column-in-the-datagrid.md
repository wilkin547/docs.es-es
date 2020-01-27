---
title: Deshabilitar botones en una columna de botón en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745950"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e2293-102">Cómo: Deshabilitar botones en una columna de botones del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2293-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e2293-103">El control <xref:System.Windows.Forms.DataGridView> incluye la clase <xref:System.Windows.Forms.DataGridViewButtonCell> para mostrar celdas con una interfaz de usuario (IU) como un botón.</span><span class="sxs-lookup"><span data-stu-id="e2293-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="e2293-104">Sin embargo, <xref:System.Windows.Forms.DataGridViewButtonCell> no proporciona una manera de deshabilitar el aspecto del botón mostrado por la celda.</span><span class="sxs-lookup"><span data-stu-id="e2293-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="e2293-105">En el ejemplo de código siguiente, se muestra cómo personalizar la clase <xref:System.Windows.Forms.DataGridViewButtonCell> para mostrar botones que pueden aparecer deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="e2293-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="e2293-106">En el ejemplo se define un nuevo tipo de celda, `DataGridViewDisableButtonCell`, que deriva de <xref:System.Windows.Forms.DataGridViewButtonCell>.</span><span class="sxs-lookup"><span data-stu-id="e2293-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="e2293-107">Este tipo de celda proporciona una nueva propiedad `Enabled`, que puede establecerse en `false` para dibujar un botón deshabilitado en la celda.</span><span class="sxs-lookup"><span data-stu-id="e2293-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="e2293-108">El ejemplo también define un nuevo tipo de columna, `DataGridViewDisableButtonColumn`, que muestra objetos `DataGridViewDisableButtonCell`.</span><span class="sxs-lookup"><span data-stu-id="e2293-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="e2293-109">Para demostrar este nuevo tipo de celda y de columna, el valor actual de cada <xref:System.Windows.Forms.DataGridViewCheckBoxCell> en el elemento primario <xref:System.Windows.Forms.DataGridView> determina si la propiedad `Enabled` de la `DataGridViewDisableButtonCell` en la misma fila es `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e2293-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2293-110">Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación.</span><span class="sxs-lookup"><span data-stu-id="e2293-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="e2293-111">También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.</span><span class="sxs-lookup"><span data-stu-id="e2293-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2293-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2293-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e2293-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e2293-113">Compiling the Code</span></span>  
 <span data-ttu-id="e2293-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e2293-114">This example requires:</span></span>  
  
- <span data-ttu-id="e2293-115">Referencias a los ensamblados System, System.Drawing, System.Windows.Forms y System.Windows.Forms.VisualStyles.</span><span class="sxs-lookup"><span data-stu-id="e2293-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2293-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2293-116">See also</span></span>

- [<span data-ttu-id="e2293-117">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2293-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e2293-118">Arquitectura del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="e2293-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="e2293-119">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2293-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
