---
title: para enlazar objetos a controles DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: d5aa5cb64c7fb2b82d69d6c87134ee901b84f5c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746700"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="0b2e6-102">Cómo: Enlazar objetos a controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b2e6-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="0b2e6-103">El ejemplo de código siguiente muestra cómo enlazar una colección de objetos a un control <xref:System.Windows.Forms.DataGridView> de modo que cada objeto se muestre como una fila independiente.</span><span class="sxs-lookup"><span data-stu-id="0b2e6-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="0b2e6-104">En este ejemplo también se explica cómo mostrar una propiedad con un tipo de enumeración en <xref:System.Windows.Forms.DataGridViewComboBoxColumn> para que la lista desplegable del cuadro combinado contenga los valores de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0b2e6-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b2e6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b2e6-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b2e6-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0b2e6-106">Compiling the Code</span></span>  
 <span data-ttu-id="0b2e6-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0b2e6-107">This example requires:</span></span>  
  
- <span data-ttu-id="0b2e6-108">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0b2e6-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2e6-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b2e6-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="0b2e6-110">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b2e6-110">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0b2e6-111">Cómo: Obtener acceso a objetos enlazados a filas DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b2e6-111">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
