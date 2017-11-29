---
title: "Cómo: Agrupar controles con el control GroupBox de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d29de04b4e221105bb02e58de01344f13af69f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="288a2-102">Cómo: Agrupar controles con el control GroupBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="288a2-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="288a2-103">Formularios Windows Forms <xref:System.Windows.Forms.GroupBox> controles se utilizan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="288a2-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="288a2-104">Hay tres razones para los controles de grupo:</span><span class="sxs-lookup"><span data-stu-id="288a2-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="288a2-105">Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.</span><span class="sxs-lookup"><span data-stu-id="288a2-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="288a2-106">Para crear la agrupación de programación (de botones de radio, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="288a2-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="288a2-107">Para mover los controles como una unidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="288a2-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="288a2-108">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="288a2-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="288a2-109">Dibujar un <xref:System.Windows.Forms.GroupBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="288a2-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="288a2-110">Agregar otros controles al cuadro de grupo, cada uno de ellos dentro del cuadro de grupo de dibujo.</span><span class="sxs-lookup"><span data-stu-id="288a2-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="288a2-111">Si dispone de los controles existentes que desee incluir en un cuadro de grupo, puede seleccionar todos los controles, como cortar a ellos en el Portapapeles, seleccione la <xref:System.Windows.Forms.GroupBox> de control y, a continuación, pegarlos en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="288a2-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="288a2-112">También puede arrastrar en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="288a2-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="288a2-113">Establecer el <xref:System.Windows.Forms.GroupBox.Text%2A> propiedad del cuadro de grupo para un título apropiado.</span><span class="sxs-lookup"><span data-stu-id="288a2-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288a2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="288a2-114">See Also</span></span>  
 <xref:System.Windows.Forms.GroupBox>  
 [<span data-ttu-id="288a2-115">GroupBox (control)</span><span class="sxs-lookup"><span data-stu-id="288a2-115">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
