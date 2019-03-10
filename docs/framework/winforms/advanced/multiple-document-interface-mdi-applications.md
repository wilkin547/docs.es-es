---
title: Aplicaciones de interfaz de múltiples documentos (MDI)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717455"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="72b46-102">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="72b46-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="72b46-103">Las aplicaciones de interfaz de múltiples documentos (MDI) permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="72b46-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="72b46-104">Las aplicaciones MDI suelen tengan un elemento de menú de ventana con submenús para cambiar entre ventanas o documentos.</span><span class="sxs-lookup"><span data-stu-id="72b46-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72b46-105">Hay algunas diferencias de comportamiento entre formularios MDI y ventanas de la interfaz de único documento (SDI) en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="72b46-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="72b46-106">El `Opacity` propiedad no afecta a la apariencia de formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="72b46-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="72b46-107">Además, el <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="72b46-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72b46-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="72b46-108">In This Section</span></span>  
 [<span data-ttu-id="72b46-109">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="72b46-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="72b46-110">Proporciona instrucciones para crear el contenedor para los diferentes documentos dentro de una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="72b46-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="72b46-111">Cómo: Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="72b46-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="72b46-112">Proporciona instrucciones para crear una o varias ventanas que funcionen dentro de un formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="72b46-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="72b46-113">Cómo: Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="72b46-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="72b46-114">Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido en el Portapapeles).</span><span class="sxs-lookup"><span data-stu-id="72b46-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="72b46-115">Cómo: Enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="72b46-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="72b46-116">Proporciona instrucciones para transportar información a la ventana secundaria activa.</span><span class="sxs-lookup"><span data-stu-id="72b46-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="72b46-117">Cómo: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="72b46-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="72b46-118">Proporciona instrucciones para la colocación en mosaico, cascada u organizar las ventanas secundarias de una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="72b46-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
