---
title: Filtrar Quitar todos los adornos de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 6b2b1832898a847f54f11cca26ecd50dbd7285ff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374172"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Procedimiento Quitar todos los adornos de un elemento
En este ejemplo se muestra cómo quitar mediante programación todos los adornos de un determinado <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo de código redundante quita todos los adornos en la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.  Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.  Este código busca una matriz nula explícitamente y es ideal para aplicaciones donde se espera una matriz nula resultar relativamente común.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente. Este código no comprobar explícitamente si la matriz es null, por lo que es posible que un <xref:System.NullReferenceException> es posible que se produce la excepción.  Este código es más adecuado para aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre adornos](adorners-overview.md)
