---
title: "Cómo: Quitar un adorno de un elemento"
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
helpviewer_keywords: adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20d17ef43f99f6815334c0acbf7eb2040959751e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Cómo: Quitar un adorno de un elemento
Este ejemplo muestra cómo quitar mediante programación un adorno concreto de un determinado <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo de código detallado quita el primer adorno en la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.  Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.  Este código explícitamente busca una matriz con valores null y es ideal para las aplicaciones donde se espera una matriz con valores null con relativa frecuencia.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente. Este código no comprobar explícitamente si hay una matriz con valores null, por lo que es posible que un <xref:System.NullReferenceException> se puede producir la excepción.  Este código es ideal para las aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)
