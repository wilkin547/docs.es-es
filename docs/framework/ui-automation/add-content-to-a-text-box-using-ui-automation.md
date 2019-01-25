---
title: Agregar contenido a un cuadro de texto utilizando la UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b8f64b12400098d94d0e25590559877d61519777
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582174"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="c10fc-102">Agregar contenido a un cuadro de texto utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="c10fc-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="c10fc-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c10fc-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c10fc-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="c10fc-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c10fc-105">Este tema contiene código de ejemplo que muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para insertar texto en un cuadro de texto multilínea.</span><span class="sxs-lookup"><span data-stu-id="c10fc-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="c10fc-106">Se proporciona un método alternativo para los controles de texto multilínea y enriquecido donde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no es aplicable.</span><span class="sxs-lookup"><span data-stu-id="c10fc-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="c10fc-107">Con fines de comparación, el ejemplo también muestra cómo utilizar métodos de Win32 para lograr los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="c10fc-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c10fc-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c10fc-108">Example</span></span>  
 <span data-ttu-id="c10fc-109">Los siguientes pasos del ejemplo a través de una secuencia de los controles de texto en una aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="c10fc-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="c10fc-110">Cada control de texto se prueba para ver si un <xref:System.Windows.Automation.ValuePattern> objeto puede obtenerse mediante la <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c10fc-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="c10fc-111">Si es compatible con el control de texto <xref:System.Windows.Automation.ValuePattern>, el <xref:System.Windows.Automation.ValuePattern.SetValue%2A> método se utiliza para insertar una cadena definida por el usuario en el control de texto.</span><span class="sxs-lookup"><span data-stu-id="c10fc-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="c10fc-112">En caso contrario, el <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> se usa el método.</span><span class="sxs-lookup"><span data-stu-id="c10fc-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="c10fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c10fc-113">See also</span></span>
- [<span data-ttu-id="c10fc-114">Ejemplo de TextPattern Insert Text</span><span class="sxs-lookup"><span data-stu-id="c10fc-114">TextPattern Insert Text Sample</span></span>](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
