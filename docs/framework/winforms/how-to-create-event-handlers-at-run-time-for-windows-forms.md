---
title: "Cómo: Crear controladores de eventos en tiempo de ejecución para formularios Windows Forms"
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
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53664bcf8c776338399297687a16ec430bca128b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="fd097-102">Cómo: Crear controladores de eventos en tiempo de ejecución para formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd097-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="fd097-103">Además de crear eventos mediante Diseñador de Windows Forms, también puede crear un controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd097-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="fd097-104">Esta acción le permite conectar controladores de eventos basándose en las condiciones del código en tiempo de ejecución en lugar de conectarlos cuando se inicia el programa.</span><span class="sxs-lookup"><span data-stu-id="fd097-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="fd097-105">Para crear un controlador de eventos en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fd097-105">To create an event handler at run time</span></span>  
  
1.  <span data-ttu-id="fd097-106">Abra el formulario en el editor de código al que desee agregar un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="fd097-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2.  <span data-ttu-id="fd097-107">Agregue un método al formulario con la firma del método para el evento que desee controlar.</span><span class="sxs-lookup"><span data-stu-id="fd097-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="fd097-108">Por ejemplo, si desea controlar la <xref:System.Windows.Forms.Control.Click> eventos de un <xref:System.Windows.Forms.Button> (control), deberá crear un método como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd097-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  <span data-ttu-id="fd097-109">Agregue el código al controlador de eventos según corresponda a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd097-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4.  <span data-ttu-id="fd097-110">Determine el formulario o control para el que desea crear un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="fd097-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5.  <span data-ttu-id="fd097-111">En un método de la clase del formulario, agregue código que especifique el controlador de eventos para controlar el evento.</span><span class="sxs-lookup"><span data-stu-id="fd097-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="fd097-112">Por ejemplo, el código siguiente especifica el controlador de eventos `button1_Click` controla la <xref:System.Windows.Forms.Control.Click> eventos de un <xref:System.Windows.Forms.Button> control:</span><span class="sxs-lookup"><span data-stu-id="fd097-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="fd097-113">El <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> método mostrado en el código de Visual Basic anterior establece un controlador de eventos click del botón.</span><span class="sxs-lookup"><span data-stu-id="fd097-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd097-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd097-114">See Also</span></span>  
 [<span data-ttu-id="fd097-115">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd097-115">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="fd097-116">Información general sobre controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="fd097-116">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 [<span data-ttu-id="fd097-117">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fd097-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
