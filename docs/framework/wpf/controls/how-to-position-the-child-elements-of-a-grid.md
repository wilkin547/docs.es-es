---
title: 'Cómo: Situar los elementos secundarios de un control Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 5ccdcb3d166e1b703faff1dc8046e61ee213d12a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187002"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="23207-102">Cómo: Situar los elementos secundarios de un control Grid</span><span class="sxs-lookup"><span data-stu-id="23207-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="23207-103">En este ejemplo se muestra cómo utilizar get y los métodos set que se definen en <xref:System.Windows.Controls.Grid> para situar elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="23207-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23207-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23207-104">Example</span></span>  
 <span data-ttu-id="23207-105">En el ejemplo siguiente se define un elemento primario <xref:System.Windows.Controls.Grid> elemento (`grid1`) que tiene tres columnas y tres filas.</span><span class="sxs-lookup"><span data-stu-id="23207-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="23207-106">Un elemento secundario <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) se agrega a la <xref:System.Windows.Controls.Grid> en posición cero de la columna, posición cero de la fila.</span><span class="sxs-lookup"><span data-stu-id="23207-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="23207-107"><xref:System.Windows.Controls.Button> elementos representan los métodos que se pueden llamar para volver a colocar el <xref:System.Windows.Shapes.Rectangle> elemento dentro de la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="23207-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="23207-108">Cuando un usuario hace clic en un botón, se activa el método relacionado.</span><span class="sxs-lookup"><span data-stu-id="23207-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="23207-109">El siguiente ejemplo de código subyacente controla los métodos que el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generar eventos.</span><span class="sxs-lookup"><span data-stu-id="23207-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="23207-110">El ejemplo escribe estas llamadas a método <xref:System.Windows.Controls.TextBlock> elementos que uso relacionados con métodos get para los nuevos valores de propiedad como cadenas de salida.</span><span class="sxs-lookup"><span data-stu-id="23207-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="23207-111">Aquí es el resultado final.</span><span class="sxs-lookup"><span data-stu-id="23207-111">Here is the finished result!</span></span>
 
 ![una captura de pantalla muestra una interfaz de usuario WPF con dos columnas, la derecha tiene una cuadrícula de 3 x 3 y la izquierda tiene botones para mover un rectángulo de color entre las columnas y filas de la cuadrícula](./media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="23207-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="23207-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="23207-114">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="23207-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
