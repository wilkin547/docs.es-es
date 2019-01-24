---
title: Procedimiento Compartir propiedades de ajuste de tamaño entre elementos Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: e415cb8bf5d2eb53926ae885ba18685390a61201
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694105"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="e94c5-102">Procedimiento Compartir propiedades de ajuste de tamaño entre elementos Grid</span><span class="sxs-lookup"><span data-stu-id="e94c5-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="e94c5-103">En este ejemplo se muestra cómo compartir los datos de ajuste de tamaño de columnas y filas entre <xref:System.Windows.Controls.Grid> elementos con el fin de mantener un tamaño coherente.</span><span class="sxs-lookup"><span data-stu-id="e94c5-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e94c5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e94c5-104">Example</span></span>  
 <span data-ttu-id="e94c5-105">El siguiente ejemplo presentan dos <xref:System.Windows.Controls.Grid> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="e94c5-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="e94c5-106">El <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> adjunta la propiedad de <xref:System.Windows.Controls.Grid> se define en el elemento primario <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="e94c5-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="e94c5-107">En el ejemplo se manipula el valor de propiedad mediante dos <xref:System.Windows.Controls.Button> elementos; cada elemento representa uno de los valores de propiedad booleana.</span><span class="sxs-lookup"><span data-stu-id="e94c5-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="e94c5-108">Cuando el <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> el valor de propiedad se establece en `true`, cada miembro de columna o fila de una <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> comparte la información de ajuste de tamaño, independientemente del contenido de una fila o columna.</span><span class="sxs-lookup"><span data-stu-id="e94c5-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="e94c5-109">...</span><span class="sxs-lookup"><span data-stu-id="e94c5-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="e94c5-110">El siguiente ejemplo de código subyacente controla los métodos que el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="e94c5-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="e94c5-111">El ejemplo escribe los resultados de estas llamadas a método <xref:System.Windows.Controls.TextBlock> elementos que uso relacionados con métodos get para los nuevos valores de propiedad como cadenas de salida.</span><span class="sxs-lookup"><span data-stu-id="e94c5-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e94c5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e94c5-112">See also</span></span>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="e94c5-113">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="e94c5-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
