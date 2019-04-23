---
title: Procedimiento para dibujar una línea en un formulario Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: aab04b9236175cedd154b817db5a6f6450503105
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074454"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="6e535-102">Procedimiento para dibujar una línea en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e535-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="6e535-103">En este ejemplo se dibuja una línea en un formulario.</span><span class="sxs-lookup"><span data-stu-id="6e535-103">This example draws a line on a form.</span></span> <span data-ttu-id="6e535-104">Normalmente, cuando se dibuja en un formulario, controla el formulario <xref:System.Windows.Forms.Control.Paint> eventos y realizar el dibujo con el <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> propiedad de la <xref:System.Windows.Forms.PaintEventArgs>, tal y como se muestra en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e535-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e535-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e535-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e535-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6e535-106">Compiling the Code</span></span>  
 <span data-ttu-id="6e535-107">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="6e535-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6e535-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="6e535-108">Robust Programming</span></span>  
 <span data-ttu-id="6e535-109">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como <xref:System.Drawing.Pen> objetos.</span><span class="sxs-lookup"><span data-stu-id="6e535-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e535-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e535-110">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="6e535-111">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="6e535-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="6e535-112">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="6e535-112">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="6e535-113">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e535-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
