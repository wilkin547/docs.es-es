---
title: 'Cómo: Comprobar la igualdad y la desigualdad de estructuras Test Point4D'
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: 1ec844c8fb0aceaaec6030c2e9d5cb30cf984f43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559819"
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
