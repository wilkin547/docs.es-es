---
title: Procedimiento para dibujar una línea en un formulario Windows Forms
description: Para obtener información sobre cómo dibujar una línea en un formulario, controle el evento Paint y, a continuación, realice el dibujo con la propiedad Graphics de PaintEventArgs.
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
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621631"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="f85df-103">Procedimiento para dibujar una línea en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f85df-103">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="f85df-104">En este ejemplo se dibuja una línea en un formulario.</span><span class="sxs-lookup"><span data-stu-id="f85df-104">This example draws a line on a form.</span></span> <span data-ttu-id="f85df-105">Normalmente, cuando se dibuja en un formulario, se controla el evento del formulario <xref:System.Windows.Forms.Control.Paint> y se realiza el dibujo mediante la <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> propiedad de <xref:System.Windows.Forms.PaintEventArgs> , como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f85df-105">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="f85df-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f85df-106">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f85df-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f85df-107">Compiling the Code</span></span>  
 <span data-ttu-id="f85df-108">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f85df-108">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f85df-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f85df-109">Robust Programming</span></span>  
 <span data-ttu-id="f85df-110">Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en todos los objetos que consumen recursos del sistema, como los <xref:System.Drawing.Pen> objetos.</span><span class="sxs-lookup"><span data-stu-id="f85df-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85df-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f85df-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="f85df-112">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="f85df-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="f85df-113">Uso de un lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="f85df-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="f85df-114">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f85df-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
