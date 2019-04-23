---
title: Procedimiento Situar los elementos secundarios de un control Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: c508f45c1ea3d0925503d6fe5600498a0558d5ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202994"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Procedimiento Situar los elementos secundarios de un control Grid
En este ejemplo se muestra cómo utilizar get y los métodos set que se definen en <xref:System.Windows.Controls.Grid> para situar elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un elemento primario <xref:System.Windows.Controls.Grid> elemento (`grid1`) que tiene tres columnas y tres filas. Un elemento secundario <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) se agrega a la <xref:System.Windows.Controls.Grid> en posición cero de la columna, posición cero de la fila. <xref:System.Windows.Controls.Button> elementos representan los métodos que se pueden llamar para volver a colocar el <xref:System.Windows.Shapes.Rectangle> elemento dentro de la <xref:System.Windows.Controls.Grid>. Cuando un usuario hace clic en un botón, se activa el método relacionado.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 El siguiente ejemplo de código subyacente controla los métodos que el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generar eventos. El ejemplo escribe estas llamadas a método <xref:System.Windows.Controls.TextBlock> elementos que uso relacionados con métodos get para los nuevos valores de propiedad como cadenas de salida.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Aquí es el resultado final.
 
 ![una captura de pantalla muestra una interfaz de usuario WPF con dos columnas, la derecha tiene una cuadrícula de 3 x 3 y la izquierda tiene botones para mover un rectángulo de color entre las columnas y filas de la cuadrícula](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Grid>
- [Información general sobre elementos Panel](panels-overview.md)
