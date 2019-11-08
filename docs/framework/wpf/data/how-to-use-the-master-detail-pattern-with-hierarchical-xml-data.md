---
title: 'Cómo: Usar el patrón principal-detalle con datos XML jerárquicos'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733416"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="6e264-102">Cómo: Usar el patrón principal-detalle con datos XML jerárquicos</span><span class="sxs-lookup"><span data-stu-id="6e264-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="6e264-103">Este ejemplo muestra cómo implementar el escenario principal-detalle con datos XML.</span><span class="sxs-lookup"><span data-stu-id="6e264-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e264-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e264-104">Example</span></span>  
 <span data-ttu-id="6e264-105">Este ejemplo es la versión de datos XML del ejemplo que se describe en [uso del patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e264-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="6e264-106">En este ejemplo, los datos proceden del archivo `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="6e264-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="6e264-107">Observe cómo el tercer control de <xref:System.Windows.Controls.ListBox> realiza un seguimiento de los cambios de selección en el segundo <xref:System.Windows.Controls.ListBox> enlazando a su propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="6e264-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="6e264-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e264-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="6e264-109">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="6e264-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
