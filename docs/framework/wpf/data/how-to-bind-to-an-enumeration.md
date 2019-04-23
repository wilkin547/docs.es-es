---
title: Procedimiento Enlazar a una enumeración
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 5026261366d6abde82790f05780d8ba2c29c4a49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210027"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="74400-102">Procedimiento Enlazar a una enumeración</span><span class="sxs-lookup"><span data-stu-id="74400-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="74400-103">En este ejemplo se muestra cómo enlazar a una enumeración enlazando al método GetValues de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="74400-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74400-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74400-104">Example</span></span>  
 <span data-ttu-id="74400-105">En el ejemplo siguiente, la <xref:System.Windows.Controls.ListBox> muestra la lista de <xref:System.Windows.HorizontalAlignment> valores de enumeración mediante enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="74400-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="74400-106">El <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.Button> se enlazan de forma que pueda cambiar la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> el valor de propiedad el <xref:System.Windows.Controls.Button> seleccionando un valor en el <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="74400-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="74400-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="74400-107">See also</span></span>

- [<span data-ttu-id="74400-108">Enlazar a un método</span><span class="sxs-lookup"><span data-stu-id="74400-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="74400-109">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="74400-109">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="74400-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="74400-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
