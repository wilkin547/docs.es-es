---
title: "Aplicaciones de interfaz de múltiples documentos (MDI)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c122931b0a00f487ddab07550913988462cfd50e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="0eca3-102">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="0eca3-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="0eca3-103">Aplicaciones de interfaz de múltiples documentos (MDI) permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="0eca3-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="0eca3-104">Las aplicaciones MDI suelen tengan un elemento de menú Ventana con submenús que permiten cambiar entre ventanas o documentos.</span><span class="sxs-lookup"><span data-stu-id="0eca3-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0eca3-105">Hay algunas diferencias de comportamiento entre formularios MDI y ventanas de la interfaz de único documento (SDI) en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0eca3-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="0eca3-106">El `Opacity` propiedad no afecta a la apariencia de formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="0eca3-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="0eca3-107">Además, la <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="0eca3-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0eca3-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0eca3-108">In This Section</span></span>  
 [<span data-ttu-id="0eca3-109">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="0eca3-109">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="0eca3-110">Proporciona instrucciones para crear el contenedor para los distintos documentos dentro de una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="0eca3-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="0eca3-111">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="0eca3-111">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="0eca3-112">Proporciona instrucciones para crear una o varias ventanas que se ejecutan dentro de un formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="0eca3-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="0eca3-113">Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="0eca3-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="0eca3-114">Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido en el Portapapeles).</span><span class="sxs-lookup"><span data-stu-id="0eca3-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="0eca3-115">Enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="0eca3-115">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="0eca3-116">Proporciona instrucciones para transportar la información de la ventana secundaria activa.</span><span class="sxs-lookup"><span data-stu-id="0eca3-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="0eca3-117">Cómo: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="0eca3-117">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="0eca3-118">Proporciona instrucciones para la disposición en mosaico, en cascada y organizar las ventanas secundarias de una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="0eca3-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
