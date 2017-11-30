---
title: "Cómo: Crear un pincel sólido"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01c07c132a703d6fd9401d9c191f5467667cc156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-solid-brush"></a>Cómo: Crear un pincel sólido
Este ejemplo se crea un <xref:System.Drawing.SolidBrush> objeto que puede utilizarse por un <xref:System.Drawing.Graphics> objeto para rellenar formas.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Cuando haya terminado de usarlos, debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consumen recursos del sistema, como los objetos de pincel.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.SolidBrush>  
 <xref:System.Drawing.Brush>  
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Pinceles y formas rellenas en GDI+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
