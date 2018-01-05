---
title: "Cómo: Enlazar a datos un control ListBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4701fe99231e115eb8cb14f7c1e5e003928bc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="6a021-102">Cómo: Enlazar a datos un control ListBox</span><span class="sxs-lookup"><span data-stu-id="6a021-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="6a021-103">Puede crear un programador de aplicaciones <xref:System.Windows.Controls.ListBox> controles sin especificar el contenido de cada <xref:System.Windows.Controls.ListBoxItem> por separado.</span><span class="sxs-lookup"><span data-stu-id="6a021-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="6a021-104">Puede utilizar el enlace de datos para enlazar datos a los elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="6a021-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="6a021-105">En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.ListBox> que rellena la <xref:System.Windows.Controls.ListBoxItem> elementos mediante un enlace de datos a un origen de datos denominado *colores*.</span><span class="sxs-lookup"><span data-stu-id="6a021-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="6a021-106">En este caso no es necesario utilizar <xref:System.Windows.Controls.ListBoxItem> etiquetas para especificar el contenido de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="6a021-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a021-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a021-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6a021-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a021-108">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [<span data-ttu-id="6a021-109">Controles</span><span class="sxs-lookup"><span data-stu-id="6a021-109">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
