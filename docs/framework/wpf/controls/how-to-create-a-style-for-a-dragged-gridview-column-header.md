---
title: Procedimiento Crear un estilo para un encabezado de columna de GridView arrastrado
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910889"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="5cd05-102">Procedimiento Crear un estilo para un encabezado de columna de GridView arrastrado</span><span class="sxs-lookup"><span data-stu-id="5cd05-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="5cd05-103">En este ejemplo se muestra cómo cambiar la apariencia de un arrastrado <xref:System.Windows.Controls.GridViewColumnHeader> cuando el usuario cambia la posición de una columna.</span><span class="sxs-lookup"><span data-stu-id="5cd05-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cd05-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cd05-104">Example</span></span>  
 <span data-ttu-id="5cd05-105">Cuando se arrastra un encabezado de columna a otra ubicación en un <xref:System.Windows.Controls.ListView> que usa <xref:System.Windows.Controls.GridView> para el modo de vista, la columna se mueve a la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="5cd05-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="5cd05-106">Mientras arrastra el encabezado de columna, aparece una copia flotante del encabezado además del encabezado original.</span><span class="sxs-lookup"><span data-stu-id="5cd05-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="5cd05-107">Un encabezado de columna en un <xref:System.Windows.Controls.GridView> se representa mediante un <xref:System.Windows.Controls.GridViewColumnHeader> objeto.</span><span class="sxs-lookup"><span data-stu-id="5cd05-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="5cd05-108">Para personalizar la apariencia de los encabezados de punto flotantes y originales, puede establecer <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> para modificar el <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="5cd05-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="5cd05-109">Estos <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> se aplican cuando la <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es el valor de propiedad `true` y <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> es el valor de propiedad <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="5cd05-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="5cd05-110">Cuando el usuario presiona el botón del mouse y mantiene presionado mientras el mouse se detiene en el <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cambia el valor de propiedad para `true`.</span><span class="sxs-lookup"><span data-stu-id="5cd05-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="5cd05-111">Del mismo modo, cuando el usuario comienza la operación de arrastrar, el <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> propiedad cambia a <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="5cd05-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="5cd05-112">El ejemplo siguiente muestra cómo establecer <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> para cambiar la <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.Background%2A> colores de los encabezados originales y de punto flotantes cuando el usuario arrastra una columna a una nueva posición.</span><span class="sxs-lookup"><span data-stu-id="5cd05-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="5cd05-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cd05-113">See also</span></span>

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="5cd05-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5cd05-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="5cd05-115">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="5cd05-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="5cd05-116">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="5cd05-116">GridView Overview</span></span>](gridview-overview.md)
