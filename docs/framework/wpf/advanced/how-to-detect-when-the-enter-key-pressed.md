---
title: 'Cómo: Detectar cuándo se presiona la tecla ENTRAR'
description: Detecta cuándo se selecciona la tecla entrar en el teclado en Windows Presentation Foundation. Este ejemplo consta de XAML y un archivo de código subyacente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163184"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="15b77-104">Cómo: Detectar cuándo se presiona la tecla ENTRAR</span><span class="sxs-lookup"><span data-stu-id="15b77-104">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="15b77-105">Este ejemplo muestra cómo detectar cuándo <xref:System.Windows.Input.Key.Enter> se presiona la tecla en el teclado.</span><span class="sxs-lookup"><span data-stu-id="15b77-105">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="15b77-106">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="15b77-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15b77-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15b77-107">Example</span></span>  
 <span data-ttu-id="15b77-108">Cuando el usuario presiona la <xref:System.Windows.Input.Key.Enter> tecla en la <xref:System.Windows.Controls.TextBox> , la entrada en el cuadro de texto aparece en otra área de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15b77-108">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="15b77-109">En el código XAML siguiente se crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.StackPanel> , un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="15b77-109">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="15b77-110">El siguiente código subyacente crea el <xref:System.Windows.UIElement.KeyDown> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="15b77-110">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="15b77-111">Si la tecla que se presiona es la <xref:System.Windows.Input.Key.Enter> tecla, se muestra un mensaje en el <xref:System.Windows.Controls.TextBlock> .</span><span class="sxs-lookup"><span data-stu-id="15b77-111">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="15b77-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="15b77-112">See also</span></span>

- [<span data-ttu-id="15b77-113">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="15b77-113">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="15b77-114">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="15b77-114">Routed Events Overview</span></span>](routed-events-overview.md)
