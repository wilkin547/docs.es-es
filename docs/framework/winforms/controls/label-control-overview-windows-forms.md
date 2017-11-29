---
title: "Información general sobre el control Label (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f55cfb6afa8ad533aac84b391a7cd6fef83d72d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="ad4d7-102">Información general sobre el control Label (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ad4d7-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="ad4d7-103">Formularios Windows Forms <xref:System.Windows.Forms.Label> controles se utilizan para mostrar texto o imágenes que no se puede editar el usuario.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="ad4d7-104">Se usan para identificar los objetos en un formulario, para proporcionar una descripción de qué cierto control realizará si hace clic en, por ejemplo, o para mostrar información en respuesta a un evento de tiempo de ejecución o el proceso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="ad4d7-105">Por ejemplo, puede utilizar etiquetas para agregar títulos descriptivos a cuadros de texto, cuadros de lista, cuadros combinados y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="ad4d7-106">También puede escribir código que cambia el texto mostrado por una etiqueta en respuesta a eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="ad4d7-107">Por ejemplo, si la aplicación tarda unos minutos en procesar un cambio, puede mostrar un mensaje de estado de procesamiento en una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="ad4d7-108">Trabajar con el Control de etiqueta</span><span class="sxs-lookup"><span data-stu-id="ad4d7-108">Working with the Label Control</span></span>  
 <span data-ttu-id="ad4d7-109">Dado que el <xref:System.Windows.Forms.Label> control no puede recibir el foco, también se puede utilizar para crear claves de acceso para otros controles.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="ad4d7-110">Una tecla de acceso permite al usuario seleccionar el otro control presionando la tecla ALT y la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="ad4d7-111">Para obtener más información, consulte [crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) y [Cómo: crear teclas de acceso con controles Label de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ad4d7-111">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="ad4d7-112">El título que se muestra en la etiqueta se encuentra en la <xref:System.Windows.Forms.Label.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="ad4d7-113">El <xref:System.Windows.Forms.Label.TextAlign%2A> propiedad le permite establecer la alineación del texto dentro de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ad4d7-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="ad4d7-114">Para obtener más información, consulte [Cómo: establecer el texto que se muestra en un Control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="ad4d7-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad4d7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad4d7-115">See Also</span></span>  
 <xref:System.Windows.Forms.Label>  
 [<span data-ttu-id="ad4d7-116">Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido</span><span class="sxs-lookup"><span data-stu-id="ad4d7-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="ad4d7-117">Crear teclas de acceso con controles Label de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad4d7-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
