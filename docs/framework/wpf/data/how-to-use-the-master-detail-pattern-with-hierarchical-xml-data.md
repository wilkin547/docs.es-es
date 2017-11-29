---
title: "Cómo: Usar el patrón principal-detalle con datos XML jerárquicos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b28a2220b5fc86654fe054deb9180450025f72f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="bc738-102">Cómo: Usar el patrón principal-detalle con datos XML jerárquicos</span><span class="sxs-lookup"><span data-stu-id="bc738-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="bc738-103">Este ejemplo muestra cómo implementar el escenario principal-detalle con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="bc738-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc738-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc738-104">Example</span></span>  
 <span data-ttu-id="bc738-105">En este ejemplo es el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] versión de datos del ejemplo se describe en [usar el patrón principal-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="bc738-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="bc738-106">En este ejemplo, los datos están en el archivo `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="bc738-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="bc738-107">Tenga en cuenta cómo el tercero <xref:System.Windows.Controls.ListBox> control realiza un seguimiento de cambios de selección en el segundo <xref:System.Windows.Controls.ListBox> mediante un enlace a su <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc738-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="bc738-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc738-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="bc738-109">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="bc738-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
