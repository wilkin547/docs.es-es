---
title: "Cómo: Dibujar una elipse rellena en Windows Forms"
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
f1_keywords: Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12b17f92fc90cde1e0c1841fc7f9d63728d50294
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="c5b45-102">Cómo: Dibujar una elipse rellena en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5b45-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="c5b45-103">En este ejemplo se dibuja una elipse rellena en un formulario.</span><span class="sxs-lookup"><span data-stu-id="c5b45-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5b45-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5b45-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5b45-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c5b45-105">Compiling the Code</span></span>  
 <span data-ttu-id="c5b45-106">No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c5b45-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="c5b45-107">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño o lo ocultan con otra forma.</span><span class="sxs-lookup"><span data-stu-id="c5b45-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="c5b45-108">Para que el contenido automáticamente volver a dibujar, debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c5b45-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c5b45-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c5b45-109">Robust Programming</span></span>  
 <span data-ttu-id="c5b45-110">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consumen recursos del sistema, como <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics> objetos.</span><span class="sxs-lookup"><span data-stu-id="c5b45-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b45-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5b45-111">See Also</span></span>  
 [<span data-ttu-id="c5b45-112">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5b45-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="c5b45-113">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="c5b45-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="c5b45-114">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="c5b45-114">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="c5b45-115">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="c5b45-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
