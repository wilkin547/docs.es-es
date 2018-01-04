---
title: "Cómo: Implementar un adorno"
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76bceae5b69fad4c217127617309484edcf18108
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-an-adorner"></a>Cómo: Implementar un adorno
Este ejemplo muestra una implementación del adorno mínima.  
  
## <a name="notes-for-implementers"></a>Notas para los implementadores  
 Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.   Una manera común de implementar el comportamiento de representación es invalidar la <xref:System.Windows.UIElement.OnRender%2A> método y el uso de uno o más <xref:System.Windows.Media.DrawingContext> objetos para representar objetos visuales del adorno según sea necesario (como se muestra en este ejemplo).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Un adorno personalizado se crea implementando una clase que hereda de la clase abstracta <xref:System.Windows.Documents.Adorner> clase.  El adorno del ejemplo simplemente adorna las esquinas de una <xref:System.Windows.UIElement> con un círculo invalidando el <xref:System.Windows.UIElement.OnRender%2A> método.  
  
### <a name="code"></a>Código  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)
