---
title: 'Cómo: Situar los elementos secundarios de un control Grid'
description: Aprenda a usar los métodos GET y set que se definen en una cuadrícula de Windows Presentation Foundation para colocar los elementos secundarios.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167395"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="93854-103">Cómo: Situar los elementos secundarios de un control Grid</span><span class="sxs-lookup"><span data-stu-id="93854-103">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="93854-104">En este ejemplo se muestra cómo usar los métodos GET y set definidos en <xref:System.Windows.Controls.Grid> para colocar los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="93854-104">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93854-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93854-105">Example</span></span>  
 <span data-ttu-id="93854-106">En el ejemplo siguiente se define un <xref:System.Windows.Controls.Grid> elemento primario ( `grid1` ) que tiene tres columnas y tres filas.</span><span class="sxs-lookup"><span data-stu-id="93854-106">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="93854-107"><xref:System.Windows.Shapes.Rectangle>Se agrega un elemento secundario ( `rect1` ) a la <xref:System.Windows.Controls.Grid> posición de la columna cero, posición de fila cero.</span><span class="sxs-lookup"><span data-stu-id="93854-107">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="93854-108"><xref:System.Windows.Controls.Button>los elementos representan métodos a los que se puede llamar para cambiar la posición del <xref:System.Windows.Shapes.Rectangle> elemento dentro de <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="93854-108"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="93854-109">Cuando un usuario hace clic en un botón, se activa el método relacionado.</span><span class="sxs-lookup"><span data-stu-id="93854-109">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="93854-110">En el siguiente ejemplo de código subyacente se administran los métodos que <xref:System.Windows.Controls.Primitives.ButtonBase.Click> provocan los eventos de botón.</span><span class="sxs-lookup"><span data-stu-id="93854-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="93854-111">En el ejemplo se escriben estas llamadas a métodos en <xref:System.Windows.Controls.TextBlock> elementos que utilizan métodos Get relacionados para generar los nuevos valores de propiedad como cadenas.</span><span class="sxs-lookup"><span data-stu-id="93854-111">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="93854-112">Este es el resultado final.</span><span class="sxs-lookup"><span data-stu-id="93854-112">Here is the finished result!</span></span>

 ![una captura de pantalla muestra una interfaz de usuario de WPF con dos columnas, el lado derecho tiene una cuadrícula de 3 x 3 y la izquierda tiene botones para desplazar un rectángulo de color entre las columnas y filas de la cuadrícula.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="93854-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="93854-114">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="93854-115">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="93854-115">Panels Overview</span></span>](panels-overview.md)
