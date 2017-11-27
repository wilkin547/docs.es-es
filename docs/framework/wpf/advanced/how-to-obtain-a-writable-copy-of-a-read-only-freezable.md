---
title: "Cómo: Obtener una copia modificable de un elemento Freezable de sólo lectura"
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
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6925e9322063d68d0d7f8c8e048eed254cd14ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Cómo: Obtener una copia modificable de un elemento Freezable de sólo lectura
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Freezable.Clone%2A> método para crear una copia modificable de solo lectura <xref:System.Windows.Freezable>.  
  
 Después de un <xref:System.Windows.Freezable> objeto se marca como de solo lectura ("inmovilizado"), no se puede modificar. Sin embargo, puede usar el <xref:System.Windows.Freezable.Clone%2A> método para crear un clon modificable del objeto inmovilizado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un clon modificable de inmovilizado <xref:System.Windows.Media.SolidColorBrush> objeto.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> los objetos, vea la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
