---
title: 'Cómo: Llevar a cabo operaciones de arrastrar y colocar entre aplicaciones'
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
ms.openlocfilehash: 13e884b6afb8fbe7248e59009e89ed749d5727d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525235"
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="c7c38-102">Cómo: Llevar a cabo operaciones de arrastrar y colocar entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c7c38-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="c7c38-103">Realizar operaciones de arrastrar y colocar entre aplicaciones es similar a habilitar esta acción dentro de una aplicación, siempre que ambas aplicaciones implicadas se comporten según el "contrato" establecido entre las propiedades <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> y <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7c38-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="c7c38-104">En el siguiente procedimiento, usará una aplicación basada en Windows que cree y el procesador de textos WordPad que se incluye con el sistema operativo Windows para realizar operaciones de arrastrar y colocar entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c7c38-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="c7c38-105">WordPad tiene un determinado conjunto de efectos permitidos para el texto que se va a arrastrar y colocar; la aplicación basada en Windows para la que escribirá el código trabajará con estos efectos para que las operaciones de arrastrar y colocar puedan completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="c7c38-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="c7c38-106">Para realizar un procedimiento de arrastrar y colocar entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c7c38-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1.  <span data-ttu-id="c7c38-107">Cree una nueva aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c7c38-107">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="c7c38-108">Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="c7c38-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3.  <span data-ttu-id="c7c38-109">Configure el control <xref:System.Windows.Forms.TextBox> para recibir datos colocados.</span><span class="sxs-lookup"><span data-stu-id="c7c38-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="c7c38-110">Para obtener más información, consulte [Tutorial: realizar una operación de arrastrar y colocar en formularios Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c7c38-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4.  <span data-ttu-id="c7c38-111">Ejecute la aplicación basada en Windows y, mientras la aplicación se está ejecutando, ejecute WordPad.</span><span class="sxs-lookup"><span data-stu-id="c7c38-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="c7c38-112">WordPad es un editor de texto instalado por Windows que permite operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="c7c38-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="c7c38-113">Es accesible presionando el **iniciar** botón Seleccionar **ejecutar**y, a continuación, escriba `WordPad` en el cuadro de texto de la **ejecutar** cuadro de diálogo y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c7c38-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5.  <span data-ttu-id="c7c38-114">Una vez abierto WordPad, escriba una cadena de texto en él.</span><span class="sxs-lookup"><span data-stu-id="c7c38-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6.  <span data-ttu-id="c7c38-115">Use el mouse para seleccionar el texto y, después, arrastre el texto seleccionado al control <xref:System.Windows.Forms.TextBox> de la aplicación basada en Windows.</span><span class="sxs-lookup"><span data-stu-id="c7c38-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="c7c38-116">Observe que, cuando el mouse se desplaza sobre el control <xref:System.Windows.Forms.TextBox> (y, por lo tanto, se genera el evento <xref:System.Windows.Forms.Control.DragEnter>), el cursor cambia y puede colocar el texto seleccionado en el control <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="c7c38-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="c7c38-117">También puede configurar su control <xref:System.Windows.Forms.TextBox> para poder arrastrar y colocar cadenas de texto en WordPad.</span><span class="sxs-lookup"><span data-stu-id="c7c38-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="c7c38-118">Para obtener más información, consulte [Tutorial: realizar una operación de arrastrar y colocar en formularios Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c7c38-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c38-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7c38-119">See Also</span></span>  
 [<span data-ttu-id="c7c38-120">Agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="c7c38-120">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="c7c38-121">Recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="c7c38-121">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [<span data-ttu-id="c7c38-122">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="c7c38-122">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
