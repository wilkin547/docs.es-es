---
title: Aplicaciones de interfaz de múltiples documentos (MDI)
description: Obtenga información sobre cómo Windows Forms las aplicaciones de interfaz de múltiples documentos (MDI) le permiten mostrar varios documentos al mismo tiempo, y cada documento se muestra en su propia ventana.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174658"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="4fd60-103">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="4fd60-103">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="4fd60-104">Las aplicaciones de interfaz de múltiples documentos (MDI) le permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="4fd60-104">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="4fd60-105">Las aplicaciones MDI suelen tener un elemento de menú Ventana con submenús para cambiar entre ventanas o documentos.</span><span class="sxs-lookup"><span data-stu-id="4fd60-105">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4fd60-106">Hay algunas diferencias de comportamiento entre los formularios MDI y las ventanas de la interfaz de un único documento (SDI) en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4fd60-106">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="4fd60-107">La `Opacity` propiedad no afecta a la apariencia de los formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="4fd60-107">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="4fd60-108">Además, el <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="4fd60-108">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4fd60-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4fd60-109">In This Section</span></span>  
 [<span data-ttu-id="4fd60-110">Procedimiento para crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="4fd60-110">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="4fd60-111">Proporciona instrucciones para crear el contenedor para varios documentos dentro de una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="4fd60-111">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="4fd60-112">Procedimiento para crear formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="4fd60-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="4fd60-113">Proporciona instrucciones para crear una o más ventanas que funcionan en un formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="4fd60-113">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="4fd60-114">Procedimiento para determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="4fd60-114">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="4fd60-115">Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido al portapapeles).</span><span class="sxs-lookup"><span data-stu-id="4fd60-115">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="4fd60-116">Procedimiento para enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="4fd60-116">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="4fd60-117">Proporciona instrucciones para transportar información a la ventana secundaria activa.</span><span class="sxs-lookup"><span data-stu-id="4fd60-117">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="4fd60-118">Procedimiento para organizar formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="4fd60-118">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="4fd60-119">Proporciona instrucciones para colocar en mosaico, en cascada u organizar las ventanas secundarias de una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="4fd60-119">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
