---
title: 'Cómo: Crear un efecto de activación mediante eventos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: ccdc8aeb26b538814b2f9020e1e3a5b311fa5a99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460163"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="03427-102">Cómo: Crear un efecto de activación mediante eventos</span><span class="sxs-lookup"><span data-stu-id="03427-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="03427-103">En este ejemplo se muestra cómo cambiar el color de un elemento a medida que el puntero del Mouse entra y sale del área ocupada por el elemento.</span><span class="sxs-lookup"><span data-stu-id="03427-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="03427-104">Este ejemplo consta de un archivo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="03427-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03427-105">En este ejemplo se muestra cómo utilizar los eventos, pero la manera recomendada de lograr este mismo efecto es usar una <xref:System.Windows.Trigger> en un estilo.</span><span class="sxs-lookup"><span data-stu-id="03427-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="03427-106">Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="03427-106">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03427-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03427-107">Example</span></span>  
 <span data-ttu-id="03427-108">El código XAML siguiente crea la interfaz de usuario, que consta de <xref:System.Windows.Controls.Border> alrededor de un <xref:System.Windows.Controls.TextBlock>, y asocia los controladores de eventos <xref:System.Windows.Input.Mouse.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> a la <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="03427-108">The following XAML creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="03427-109">El siguiente código subyacente crea los controladores de eventos <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave>.</span><span class="sxs-lookup"><span data-stu-id="03427-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="03427-110">Cuando el puntero del Mouse entra en el <xref:System.Windows.Controls.Border>, el fondo del <xref:System.Windows.Controls.Border> cambia a rojo.</span><span class="sxs-lookup"><span data-stu-id="03427-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="03427-111">Cuando el puntero del mouse sale del <xref:System.Windows.Controls.Border>, el fondo del <xref:System.Windows.Controls.Border> se vuelve a cambiar a blanco.</span><span class="sxs-lookup"><span data-stu-id="03427-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
