---
title: "Cómo: Crear Windows Forms con forma"
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
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 981256c2447a53aef8e1ea676db38ce693d1337e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="e68a0-102">Cómo: Crear Windows Forms con forma</span><span class="sxs-lookup"><span data-stu-id="e68a0-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="e68a0-103">Este ejemplo da forma elíptica que cambia el tamaño con el formulario a un formulario.</span><span class="sxs-lookup"><span data-stu-id="e68a0-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e68a0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e68a0-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e68a0-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e68a0-105">Compiling the Code</span></span>  
 <span data-ttu-id="e68a0-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e68a0-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e68a0-107">Referencias a los espacios de nombres <xref:System.Windows.Forms> y <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="e68a0-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="e68a0-108">Este ejemplo se reemplaza el <xref:System.Windows.Forms.Control.OnPaint%2A> método para cambiar la forma del formulario.</span><span class="sxs-lookup"><span data-stu-id="e68a0-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="e68a0-109">Para usar este código, copie la declaración del método, así como el código de dibujo dentro del método.</span><span class="sxs-lookup"><span data-stu-id="e68a0-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e68a0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e68a0-110">See Also</span></span>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Region>  
 <xref:System.Drawing>  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 [<span data-ttu-id="e68a0-111">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="e68a0-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
