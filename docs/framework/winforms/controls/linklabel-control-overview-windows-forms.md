---
title: "Información general sobre el control LinkLabel (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73bbd04b9ef5d2d0c5457dafb794435b3a4db380
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="5df53-102">Información general sobre el control LinkLabel (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5df53-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="5df53-103">Los formularios Windows Forms <xref:System.Windows.Forms.LinkLabel> control le permite agregar vínculos de estilo Web a aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5df53-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="5df53-104">Puede usar el <xref:System.Windows.Forms.LinkLabel> control para todo lo que puede usar el <xref:System.Windows.Forms.Label> controlar para; también puede establecer parte del texto como un vínculo a un archivo, carpeta o página Web.</span><span class="sxs-lookup"><span data-stu-id="5df53-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you also can set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="5df53-105">¿Qué puede hacer con el Control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5df53-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="5df53-106">Además de todas las propiedades, métodos y eventos de la <xref:System.Windows.Forms.Label> (control), el <xref:System.Windows.Forms.LinkLabel> control tiene propiedades para los hipervínculos y los colores de la conexión.</span><span class="sxs-lookup"><span data-stu-id="5df53-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="5df53-107">El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad establece el área del texto que activa el vínculo.</span><span class="sxs-lookup"><span data-stu-id="5df53-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="5df53-108">El <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, y <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> propiedades establecen los colores del vínculo.</span><span class="sxs-lookup"><span data-stu-id="5df53-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="5df53-109">El <xref:System.Windows.Forms.LinkLabel.LinkClicked> evento determina qué ocurre cuando se selecciona el texto del vínculo.</span><span class="sxs-lookup"><span data-stu-id="5df53-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="5df53-110">El uso más simple de la <xref:System.Windows.Forms.LinkLabel> control consiste en mostrar un único vínculo mediante la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad, pero también puede mostrar varios hipervínculos con la <xref:System.Windows.Forms.LinkLabel.Links%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5df53-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="5df53-111">El <xref:System.Windows.Forms.LinkLabel.Links%2A> propiedad le permite tener acceso a una colección de vínculos.</span><span class="sxs-lookup"><span data-stu-id="5df53-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="5df53-112">También puede especificar datos en el <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> propiedad de cada persona <xref:System.Windows.Forms.LinkLabel.Link> objeto.</span><span class="sxs-lookup"><span data-stu-id="5df53-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="5df53-113">El valor de la <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> propiedad puede utilizarse para almacenar la ubicación de un archivo para mostrar o la dirección de un sitio Web.</span><span class="sxs-lookup"><span data-stu-id="5df53-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df53-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5df53-114">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="5df53-115">Información general sobre el control Label</span><span class="sxs-lookup"><span data-stu-id="5df53-115">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="5df53-116">Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5df53-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="5df53-117">Cambiar la apariencia del control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5df53-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
