---
title: 'Cómo: Situar los elementos secundarios de un control Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186720"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="465c0-102">Cómo: Situar los elementos secundarios de un control Grid</span><span class="sxs-lookup"><span data-stu-id="465c0-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="465c0-103">En este ejemplo se muestra cómo utilizar los <xref:System.Windows.Controls.Grid> métodos get y set que se definen para colocar elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="465c0-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="465c0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="465c0-104">Example</span></span>  
 <span data-ttu-id="465c0-105">En el ejemplo <xref:System.Windows.Controls.Grid> siguiente`grid1`se define un elemento primario ( ) que tiene tres columnas y tres filas.</span><span class="sxs-lookup"><span data-stu-id="465c0-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="465c0-106">Un <xref:System.Windows.Shapes.Rectangle> elemento`rect1`secundario ( ) <xref:System.Windows.Controls.Grid> se agrega a la posición de columna cero, posición de fila cero.</span><span class="sxs-lookup"><span data-stu-id="465c0-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="465c0-107"><xref:System.Windows.Controls.Button>los elementos representan métodos que <xref:System.Windows.Shapes.Rectangle> se <xref:System.Windows.Controls.Grid>pueden llamar para cambiar la posición del elemento dentro del archivo .</span><span class="sxs-lookup"><span data-stu-id="465c0-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="465c0-108">Cuando un usuario hace clic en un botón, se activa el método relacionado.</span><span class="sxs-lookup"><span data-stu-id="465c0-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="465c0-109">En el ejemplo de código subyacente <xref:System.Windows.Controls.Primitives.ButtonBase.Click> siguiente se controlan los métodos que generan los eventos de botón.</span><span class="sxs-lookup"><span data-stu-id="465c0-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="465c0-110">En el ejemplo se <xref:System.Windows.Controls.TextBlock> escriben estas llamadas de método a elementos que usan métodos get relacionados para generar los nuevos valores de propiedad como cadenas.</span><span class="sxs-lookup"><span data-stu-id="465c0-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="465c0-111">¡Aquí está el resultado final!</span><span class="sxs-lookup"><span data-stu-id="465c0-111">Here is the finished result!</span></span>

 ![una captura de pantalla muestra una interfaz de usuario DE WPF con dos columnas, el lado derecho tiene una cuadrícula de 3 x 3 y el izquierdo tiene botones para mover un rectángulo de color entre las columnas y filas de la cuadrícula](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="465c0-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="465c0-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="465c0-114">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="465c0-114">Panels Overview</span></span>](panels-overview.md)
