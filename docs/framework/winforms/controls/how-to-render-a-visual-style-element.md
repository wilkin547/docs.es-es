---
title: "Cómo: Representar un elemento de estilo visual"
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
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b96f9e6cc54e028e94cc7ae377012ac4f1328bb0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="5361e-102">Cómo: Representar un elemento de estilo visual</span><span class="sxs-lookup"><span data-stu-id="5361e-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="5361e-103">El <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> expone el espacio de nombres <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> elementos (UI) compatibles con estilos visuales de la interfaz de objetos que representan el usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="5361e-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="5361e-104">Este tema muestra cómo utilizar el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> clase para representar la <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> que representa el **cerrar sesión** y **apagar** botones del menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="5361e-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="5361e-105">Para representar un elemento de estilo visual</span><span class="sxs-lookup"><span data-stu-id="5361e-105">To render a visual style element</span></span>  
  
1.  <span data-ttu-id="5361e-106">Crear un <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> y establézcalo en el elemento que va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="5361e-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="5361e-107">Tenga en cuenta el uso de la <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> propiedad y el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> método; el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor iniciará una excepción si los estilos visuales están deshabilitados o un elemento no está definido.</span><span class="sxs-lookup"><span data-stu-id="5361e-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  <span data-ttu-id="5361e-108">Llame a la <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> método para representar el elemento que el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> representa actualmente.</span><span class="sxs-lookup"><span data-stu-id="5361e-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5361e-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5361e-109">Compiling the Code</span></span>  
 <span data-ttu-id="5361e-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="5361e-110">This example requires:</span></span>  
  
-   <span data-ttu-id="5361e-111">Un control personalizado derivado de la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="5361e-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="5361e-112">Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="5361e-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="5361e-113">Las referencias a la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, y <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="5361e-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5361e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5361e-114">See Also</span></span>  
 [<span data-ttu-id="5361e-115">Representar controles con estilos visuales</span><span class="sxs-lookup"><span data-stu-id="5361e-115">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
