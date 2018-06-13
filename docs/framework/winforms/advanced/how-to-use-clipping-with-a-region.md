---
title: 'Cómo: Utilizar el recorte en una región'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: bfc40d985ec12a30b73935ace7ef034aadbd5385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522101"
---
# <a name="how-to-use-clipping-with-a-region"></a>Cómo: Utilizar el recorte en una región
Una de las propiedades de la <xref:System.Drawing.Graphics> clase es la región de recorte. Todo el dibujo realizado un determinado <xref:System.Drawing.Graphics> está restringido a la región de recorte de ese objeto <xref:System.Drawing.Graphics> objeto. Puede establecer la región de recorte mediante una llamada a la <xref:System.Drawing.Graphics.SetClip%2A> método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una ruta de acceso que consta de un único polígono. A continuación, el código construye una región, basada en dicha ruta de acceso. La región se pasa a la <xref:System.Drawing.Graphics.SetClip%2A> método de una <xref:System.Drawing.Graphics> se dibujan los objetos y, a continuación, dos cadenas.  
  
 En la siguiente ilustración se muestra las cadenas recortadas.  
  
 ![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Regiones de GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [Utilizar regiones](../../../../docs/framework/winforms/advanced/using-regions.md)
