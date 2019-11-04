---
title: 'Cómo: Enlazar a una enumeración'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454441"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="71218-102">Cómo: Enlazar a una enumeración</span><span class="sxs-lookup"><span data-stu-id="71218-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="71218-103">En este ejemplo se muestra cómo enlazar a una enumeración enlazando al método GetValues de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="71218-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71218-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71218-104">Example</span></span>  
 <span data-ttu-id="71218-105">En el ejemplo siguiente, el <xref:System.Windows.Controls.ListBox> muestra la lista de valores de enumeración de <xref:System.Windows.HorizontalAlignment> a través del enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="71218-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="71218-106">El <xref:System.Windows.Controls.ListBox> y el <xref:System.Windows.Controls.Button> están enlazados de modo que pueda cambiar el valor de la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> del <xref:System.Windows.Controls.Button> seleccionando un valor en el <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="71218-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="71218-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="71218-107">See also</span></span>

- [<span data-ttu-id="71218-108">Enlazar a un método</span><span class="sxs-lookup"><span data-stu-id="71218-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="71218-109">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="71218-109">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="71218-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="71218-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
