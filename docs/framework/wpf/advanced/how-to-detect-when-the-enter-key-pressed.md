---
title: Procedimiento Detectar cuándo se presiona la tecla entrar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004826"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="0eded-102">Procedimiento Detectar cuándo se presiona la tecla entrar</span><span class="sxs-lookup"><span data-stu-id="0eded-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="0eded-103">Este ejemplo muestra cómo detectar cuándo se presiona la tecla <xref:System.Windows.Input.Key.Enter> en el teclado.</span><span class="sxs-lookup"><span data-stu-id="0eded-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="0eded-104">Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="0eded-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eded-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eded-105">Example</span></span>  
 <span data-ttu-id="0eded-106">Cuando el usuario presiona la tecla <xref:System.Windows.Input.Key.Enter> en el <xref:System.Windows.Controls.TextBox>, la entrada en el cuadro de texto aparece en otra área de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eded-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="0eded-107">El código XAML siguiente crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="0eded-107">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="0eded-108">El siguiente código subyacente crea el controlador de eventos <xref:System.Windows.UIElement.KeyDown>.</span><span class="sxs-lookup"><span data-stu-id="0eded-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="0eded-109">Si la tecla que se presiona es la tecla <xref:System.Windows.Input.Key.Enter>, se muestra un mensaje en el <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="0eded-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="0eded-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eded-110">See also</span></span>

- [<span data-ttu-id="0eded-111">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="0eded-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="0eded-112">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="0eded-112">Routed Events Overview</span></span>](routed-events-overview.md)
