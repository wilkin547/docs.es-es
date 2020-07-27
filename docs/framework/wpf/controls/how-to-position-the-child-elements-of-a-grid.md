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
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Cómo: Situar los elementos secundarios de un control Grid
En este ejemplo se muestra cómo usar los métodos GET y set definidos en <xref:System.Windows.Controls.Grid> para colocar los elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un <xref:System.Windows.Controls.Grid> elemento primario ( `grid1` ) que tiene tres columnas y tres filas. <xref:System.Windows.Shapes.Rectangle>Se agrega un elemento secundario ( `rect1` ) a la <xref:System.Windows.Controls.Grid> posición de la columna cero, posición de fila cero. <xref:System.Windows.Controls.Button>los elementos representan métodos a los que se puede llamar para cambiar la posición del <xref:System.Windows.Shapes.Rectangle> elemento dentro de <xref:System.Windows.Controls.Grid> . Cuando un usuario hace clic en un botón, se activa el método relacionado.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 En el siguiente ejemplo de código subyacente se administran los métodos que <xref:System.Windows.Controls.Primitives.ButtonBase.Click> provocan los eventos de botón. En el ejemplo se escriben estas llamadas a métodos en <xref:System.Windows.Controls.TextBlock> elementos que utilizan métodos Get relacionados para generar los nuevos valores de propiedad como cadenas.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Este es el resultado final.

 ![una captura de pantalla muestra una interfaz de usuario de WPF con dos columnas, el lado derecho tiene una cuadrícula de 3 x 3 y la izquierda tiene botones para desplazar un rectángulo de color entre las columnas y filas de la cuadrícula.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Grid>
- [Información general sobre elementos Panel](panels-overview.md)
