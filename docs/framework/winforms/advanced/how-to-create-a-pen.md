---
title: "Cómo: Crear un lápiz"
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
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 402881d31c14b4223144792e081324fb113162a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="b0445-102">Cómo: Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="b0445-102">How to: Create a Pen</span></span>
<span data-ttu-id="b0445-103">Este ejemplo se crea un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="b0445-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0445-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0445-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b0445-105">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b0445-105">Robust Programming</span></span>  
 <span data-ttu-id="b0445-106">Cuando haya terminado de usar objetos que consumen recursos del sistema, como <xref:System.Drawing.Pen> objetos, debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en ellos.</span><span class="sxs-lookup"><span data-stu-id="b0445-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0445-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0445-107">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="b0445-108">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="b0445-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="b0445-109">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="b0445-109">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
