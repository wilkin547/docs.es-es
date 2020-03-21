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
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Cómo: Situar los elementos secundarios de un control Grid
En este ejemplo se muestra cómo utilizar los <xref:System.Windows.Controls.Grid> métodos get y set que se definen para colocar elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Controls.Grid> siguiente`grid1`se define un elemento primario ( ) que tiene tres columnas y tres filas. Un <xref:System.Windows.Shapes.Rectangle> elemento`rect1`secundario ( ) <xref:System.Windows.Controls.Grid> se agrega a la posición de columna cero, posición de fila cero. <xref:System.Windows.Controls.Button>los elementos representan métodos que <xref:System.Windows.Shapes.Rectangle> se <xref:System.Windows.Controls.Grid>pueden llamar para cambiar la posición del elemento dentro del archivo . Cuando un usuario hace clic en un botón, se activa el método relacionado.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 En el ejemplo de código subyacente <xref:System.Windows.Controls.Primitives.ButtonBase.Click> siguiente se controlan los métodos que generan los eventos de botón. En el ejemplo se <xref:System.Windows.Controls.TextBlock> escriben estas llamadas de método a elementos que usan métodos get relacionados para generar los nuevos valores de propiedad como cadenas.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 ¡Aquí está el resultado final!

 ![una captura de pantalla muestra una interfaz de usuario DE WPF con dos columnas, el lado derecho tiene una cuadrícula de 3 x 3 y el izquierdo tiene botones para mover un rectángulo de color entre las columnas y filas de la cuadrícula](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Grid>
- [Información general sobre elementos Panel](panels-overview.md)
