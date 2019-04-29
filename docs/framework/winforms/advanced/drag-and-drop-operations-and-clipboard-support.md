---
title: Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: 5e7bb75b648163dab7e410a159d55ebbb75f1b0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756434"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="90a09-102">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="90a09-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="90a09-103">Puede habilitar las operaciones de arrastrar y colocar del usuario en una aplicación basada en Windows controlando una serie de eventos, sobre todo los eventos <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> y <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="90a09-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="90a09-104">También puede implementar la compatibilidad de cortar, copiar y pegar del usuario, y la transferencia de datos del usuario en el Portapapeles en las aplicaciones basadas en Windows mediante llamadas a métodos simples.</span><span class="sxs-lookup"><span data-stu-id="90a09-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90a09-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="90a09-105">In This Section</span></span>  
 [<span data-ttu-id="90a09-106">Tutorial: Realizar una operación de arrastrar y colocar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90a09-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="90a09-107">Explica cómo iniciar una operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="90a09-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="90a09-108">Cómo: Realizar operaciones de arrastrar y colocar entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="90a09-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="90a09-109">Ilustra cómo realizar operaciones de arrastrar y colocar entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="90a09-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="90a09-110">Cómo: Agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="90a09-110">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="90a09-111">Describe una manera de insertar información en el Portapapeles mediante programación.</span><span class="sxs-lookup"><span data-stu-id="90a09-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="90a09-112">Cómo: Recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="90a09-112">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="90a09-113">Describe cómo acceder a los datos almacenados en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="90a09-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="90a09-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="90a09-114">Related Sections</span></span>  
 [<span data-ttu-id="90a09-115">Funcionalidad de arrastrar y soltar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90a09-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="90a09-116">Describe los métodos, eventos y clases utilizadas para implementar el comportamiento de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="90a09-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="90a09-117">Describe los detalles del evento que solicita permiso para continuar la operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="90a09-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="90a09-118">Describe los detalles del método que resulta esencial para iniciar una operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="90a09-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="90a09-119">Consulte también [Cómo: Enviar datos al formulario secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="90a09-119">Also see [How to: Send Data to the Active MDI Child](how-to-send-data-to-the-active-mdi-child.md).</span></span>
