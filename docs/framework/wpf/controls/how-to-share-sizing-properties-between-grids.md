---
title: "Cómo: Compartir propiedades de ajuste de tamaño entre elementos Grid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="9a798-102">Cómo: Compartir propiedades de ajuste de tamaño entre elementos Grid</span><span class="sxs-lookup"><span data-stu-id="9a798-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="9a798-103">En este ejemplo se muestra cómo compartir los datos de ajuste de tamaño de columnas y filas entre <xref:System.Windows.Controls.Grid> elementos con el fin de mantener un tamaño coherente.</span><span class="sxs-lookup"><span data-stu-id="9a798-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a798-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a798-104">Example</span></span>  
 <span data-ttu-id="9a798-105">En el ejemplo siguiente se presenta dos <xref:System.Windows.Controls.Grid> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="9a798-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="9a798-106">El <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> adjunta la propiedad de <xref:System.Windows.Controls.Grid> se define en el registro primario <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="9a798-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="9a798-107">En el ejemplo se manipula el valor de propiedad por medio de dos <xref:System.Windows.Controls.Button> elementos; cada elemento representa uno de los valores de propiedad booleana.</span><span class="sxs-lookup"><span data-stu-id="9a798-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="9a798-108">Cuando el <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> valor de la propiedad se establece en `true`, cada miembro de columna o fila de una <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> comparte información de ajuste de tamaño, sin tener en cuenta el contenido de una fila o columna.</span><span class="sxs-lookup"><span data-stu-id="9a798-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="9a798-109">...</span><span class="sxs-lookup"><span data-stu-id="9a798-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="9a798-110">En el siguiente ejemplo de código subyacente controla los métodos que el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> genera el evento.</span><span class="sxs-lookup"><span data-stu-id="9a798-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="9a798-111">El ejemplo escribe los resultados de estas llamadas a métodos <xref:System.Windows.Controls.TextBlock> elementos que use relacionado métodos get para generar los nuevos valores de propiedad como cadenas.</span><span class="sxs-lookup"><span data-stu-id="9a798-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9a798-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a798-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [<span data-ttu-id="9a798-113">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="9a798-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
