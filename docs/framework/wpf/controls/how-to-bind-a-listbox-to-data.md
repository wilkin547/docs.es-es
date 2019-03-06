---
title: Filtrar Enlazar a datos un control ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 2cbcb0fb859605c33e2d92559b4a47aa1725472c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372886"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="c170d-102">Filtrar Enlazar a datos un control ListBox</span><span class="sxs-lookup"><span data-stu-id="c170d-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="c170d-103">Puede crear un programador de aplicaciones <xref:System.Windows.Controls.ListBox> controles sin especificar el contenido de cada <xref:System.Windows.Controls.ListBoxItem> por separado.</span><span class="sxs-lookup"><span data-stu-id="c170d-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="c170d-104">Puede usar el enlace de datos para enlazar datos a los elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="c170d-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="c170d-105">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.ListBox> que rellena la <xref:System.Windows.Controls.ListBoxItem> elementos de enlace de datos a un origen de datos denominado *colores*.</span><span class="sxs-lookup"><span data-stu-id="c170d-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="c170d-106">En este caso no es necesario utilizar <xref:System.Windows.Controls.ListBoxItem> etiquetas para especificar el contenido de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="c170d-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c170d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c170d-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c170d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c170d-108">See also</span></span>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="c170d-109">Controles</span><span class="sxs-lookup"><span data-stu-id="c170d-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
