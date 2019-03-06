---
title: Procedimiento Implementar un adorno
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: 53a25396ba5d8a5c78e850e636b7c882c03d5152
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362648"
---
# <a name="how-to-implement-an-adorner"></a>Procedimiento Implementar un adorno
Este ejemplo muestra una implementación mínima de adorno.  
  
## <a name="notes-for-implementers"></a>Notas para los implementadores  
 Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.   Una manera común de implementar el comportamiento de representación es invalidar el <xref:System.Windows.UIElement.OnRender%2A> método y el uso de uno o más <xref:System.Windows.Media.DrawingContext> objetos para representar elementos de visuales del adorno según sea necesario (como se muestra en este ejemplo).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Un adorno personalizado se crea implementando una clase que hereda de la clase abstracta <xref:System.Windows.Documents.Adorner> clase.  El adorno del ejemplo se limita adorna las esquinas de un <xref:System.Windows.UIElement> con círculos invalidando el <xref:System.Windows.UIElement.OnRender%2A> método.  
  
### <a name="code"></a>Código  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre adornos](adorners-overview.md)
