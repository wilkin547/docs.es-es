---
title: Filtrar Usar el patrón maestro y detalle con datos XML jerárquicos
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: ba6c932f519ffa5c3c70ecb21eb9b5d08c40fb28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086265"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="e478a-102">Filtrar Usar el patrón maestro y detalle con datos XML jerárquicos</span><span class="sxs-lookup"><span data-stu-id="e478a-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="e478a-103">En este ejemplo se muestra cómo implementar el escenario principal-detalle con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="e478a-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e478a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e478a-104">Example</span></span>  
 <span data-ttu-id="e478a-105">En este ejemplo es el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] versión de datos del ejemplo se describe en [usar el patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="e478a-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="e478a-106">En este ejemplo, los datos están en el archivo `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="e478a-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="e478a-107">Tenga en cuenta cómo la tercera <xref:System.Windows.Controls.ListBox> control realiza el seguimiento de cambios de selección en el segundo <xref:System.Windows.Controls.ListBox> mediante un enlace a su <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e478a-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="e478a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e478a-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="e478a-109">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e478a-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
