---
title: "Cómo: Comprobar la igualdad y la desigualdad de estructuras Test Point4D"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 849082fc1b933c4172c0d22ec3c9c2a1644a32fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>Cómo: Comprobar la igualdad y la desigualdad de estructuras Test Point4D
Este ejemplo muestra cómo probar <xref:System.Windows.Media.Media3D.Point4D> estructuras de igualdad y desigualdad.  
  
 El código siguiente muestra cómo probar <xref:System.Windows.Media.Media3D.Point4D> estructuras para la igualdad y desigualdad utilizando el <xref:System.Windows.Media.Media3D.Point4D> métodos de igualdad.  El <xref:System.Windows.Media.Media3D.Point4D> estructuras se comprueban si son iguales usando la igualdad sobrecargada (`==`) operador y, a continuación, por desigualdad mediante la desigualdad sobrecargado (`!=`) (operador) y, finalmente, un <xref:System.Windows.Media.Media3D.Point3D> estructura y un <xref:System.Windows.Media.Media3D.Point4D> estructura que se buscan son iguales usando el método estático <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> método.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
