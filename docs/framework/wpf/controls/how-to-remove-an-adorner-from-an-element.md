---
title: Filtrar Quitar un adorno de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212406"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Filtrar Quitar un adorno de un elemento
En este ejemplo se muestra cómo quitar mediante programación un adorno concreto de un determinado <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo de código redundante se quita el primer adorno de la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.  Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.  Este código busca una matriz nula explícitamente y es ideal para aplicaciones donde se espera una matriz nula resultar relativamente común.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente. Este código no comprobar explícitamente si la matriz es null, por lo que es posible que un <xref:System.NullReferenceException> es posible que se produce la excepción.  Este código es más adecuado para aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre adornos](adorners-overview.md)
