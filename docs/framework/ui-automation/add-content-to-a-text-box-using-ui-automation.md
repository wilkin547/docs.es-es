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
ms.openlocfilehash: 71385690c01d261b4ff1b495674bab377232e81d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447251"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="eb969-102">Agregar contenido a un cuadro de texto utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="eb969-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="eb969-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="eb969-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="eb969-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="eb969-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="eb969-105">Este tema contiene código de ejemplo que muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para insertar texto en un cuadro de texto de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="eb969-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="eb969-106">Se proporciona un método alternativo para los controles de texto enriquecido y multilínea donde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no es aplicable.</span><span class="sxs-lookup"><span data-stu-id="eb969-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="eb969-107">Con fines de comparación, en el ejemplo también se muestra cómo usar métodos Win32 para lograr los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="eb969-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb969-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb969-108">Example</span></span>  
 <span data-ttu-id="eb969-109">En el ejemplo siguiente se recorren los pasos de una secuencia de controles de texto en una aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="eb969-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="eb969-110">Cada control de texto se comprueba para ver si un objeto de <xref:System.Windows.Automation.ValuePattern> puede obtenerse a partir de él mediante el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb969-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="eb969-111">Si el control de texto admite <xref:System.Windows.Automation.ValuePattern>, se usa el método <xref:System.Windows.Automation.ValuePattern.SetValue%2A> para insertar una cadena definida por el usuario en el control de texto.</span><span class="sxs-lookup"><span data-stu-id="eb969-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="eb969-112">De lo contrario, se utiliza el método <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb969-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="eb969-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb969-113">See also</span></span>

- <span data-ttu-id="eb969-114">[Ejemplo de inserción de texto de TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eb969-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
