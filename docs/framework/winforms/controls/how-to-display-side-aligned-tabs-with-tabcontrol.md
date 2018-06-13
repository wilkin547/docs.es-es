---
title: 'Cómo: Mostrar pestañas alineadas a la izquierda con TabControl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
ms.openlocfilehash: e145547ba4c8648a765e9507b7f35e50cb15fd82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532466"
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a><span data-ttu-id="3f1c8-102">Cómo: Mostrar pestañas alineadas a la izquierda con TabControl</span><span class="sxs-lookup"><span data-stu-id="3f1c8-102">How to: Display Side-Aligned Tabs with TabControl</span></span>
<span data-ttu-id="3f1c8-103">La propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> de <xref:System.Windows.Forms.TabControl> permite mostrar pestañas verticalmente (a lo largo del borde izquierdo o derecho del control) en lugar de horizontalmente (en la parte superior o inferior del control).</span><span class="sxs-lookup"><span data-stu-id="3f1c8-103">The <xref:System.Windows.Forms.TabControl.Alignment%2A> property of <xref:System.Windows.Forms.TabControl> supports displaying tabs vertically (along the left or right edge of the control), as opposed to horizontally (across the top or bottom of the control).</span></span> <span data-ttu-id="3f1c8-104">De forma predeterminada, esta presentación vertical produce una mala experiencia de usuario porque la propiedad <xref:System.Windows.Forms.TabPage.Text%2A> del objeto <xref:System.Windows.Forms.TabPage> no se muestra en la pestaña cuando se habilitan estilos visuales.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-104">By default, this vertical display results in a poor user experience, because the <xref:System.Windows.Forms.TabPage.Text%2A> property of the <xref:System.Windows.Forms.TabPage> object does not display in the tab when visual styles are enabled.</span></span> <span data-ttu-id="3f1c8-105">Tampoco hay una manera directa de controlar la dirección del texto dentro de la pestaña. Puede usar la característica «dibujado por el propietario» en <xref:System.Windows.Forms.TabControl> para mejorar la experiencia.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-105">There is also no direct way to control the direction of the text within the tab. You can use owner draw on <xref:System.Windows.Forms.TabControl> to improve this experience.</span></span>  
  
 <span data-ttu-id="3f1c8-106">El procedimiento siguiente muestra cómo representar pestañas alineadas a la derecha, con el texto de la pestaña escrito de izquierda a derecha usando la característica "dibujado por el propietario".</span><span class="sxs-lookup"><span data-stu-id="3f1c8-106">The following procedure shows how to render right-aligned tabs, with the tab text running from left to right, by using the "owner draw" feature.</span></span>  
  
### <a name="to-display-right-aligned-tabs"></a><span data-ttu-id="3f1c8-107">Para mostrar pestañas alineadas a la derecha</span><span class="sxs-lookup"><span data-stu-id="3f1c8-107">To display right-aligned tabs</span></span>  
  
1.  <span data-ttu-id="3f1c8-108">Agregue un <xref:System.Windows.Forms.TabControl> al formulario.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-108">Add a <xref:System.Windows.Forms.TabControl> to your form.</span></span>  
  
2.  <span data-ttu-id="3f1c8-109">Establezca la propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> en <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-109">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property to <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
3.  <span data-ttu-id="3f1c8-110">Establezca la propiedad <xref:System.Windows.Forms.TabControl.SizeMode%2A> en <xref:System.Windows.Forms.TabSizeMode.Fixed> para que todas las pestañas tengan el mismo ancho.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-110">Set the <xref:System.Windows.Forms.TabControl.SizeMode%2A> property to <xref:System.Windows.Forms.TabSizeMode.Fixed>, so that all tabs are the same width.</span></span>  
  
4.  <span data-ttu-id="3f1c8-111">Establezca la propiedad <xref:System.Windows.Forms.TabControl.ItemSize%2A> en el tamaño fijo preferido para las pestañas.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-111">Set the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property to the preferred fixed size for the tabs.</span></span> <span data-ttu-id="3f1c8-112">Tenga en cuenta que la propiedad <xref:System.Windows.Forms.TabControl.ItemSize%2A> se comporta como si las pestañas estuvieran en la parte superior, aunque estén alineadas a la derecha.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-112">Keep in mind that the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property behaves as though the tabs were on top, although they are right-aligned.</span></span> <span data-ttu-id="3f1c8-113">Como resultado, para hacer que las pestañas sean más anchas, debe cambiar la propiedad <xref:System.Drawing.Size.Height%2A> y, para que sean más altas, debe cambiar la propiedad <xref:System.Drawing.Size.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-113">As a result, in order to make the tabs wider, you must change the <xref:System.Drawing.Size.Height%2A> property, and in order to make them taller, you must change the <xref:System.Drawing.Size.Width%2A> property.</span></span>  
  
     <span data-ttu-id="3f1c8-114">Para obtener los mejores resultados con el siguiente ejemplo de código, establezca el valor de <xref:System.Drawing.Size.Width%2A> en 25 y el valor de <xref:System.Drawing.Size.Height%2A> en 100.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-114">For best result with the code example below, set the <xref:System.Drawing.Size.Width%2A> of the tabs to 25 and the <xref:System.Drawing.Size.Height%2A> to 100.</span></span>  
  
5.  <span data-ttu-id="3f1c8-115">Establezca la propiedad <xref:System.Windows.Forms.TabControl.DrawMode%2A> en <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-115">Set the <xref:System.Windows.Forms.TabControl.DrawMode%2A> property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span></span>  
  
6.  <span data-ttu-id="3f1c8-116">Defina un controlador para el evento <xref:System.Windows.Forms.TabControl.DrawItem> de <xref:System.Windows.Forms.TabControl> que representa el texto de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="3f1c8-116">Define a handler for the <xref:System.Windows.Forms.TabControl.DrawItem> event of <xref:System.Windows.Forms.TabControl> that renders the text from left to right.</span></span>  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3f1c8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f1c8-117">See Also</span></span>  
 [<span data-ttu-id="3f1c8-118">TabControl (control)</span><span class="sxs-lookup"><span data-stu-id="3f1c8-118">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
