---
title: Filtrar para crear controladores de eventos en tiempo de ejecución para formularios Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: 3c1dca420b9e63fe8a2cb93b2e7918d9dc35e84d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158553"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="4bf81-102">Filtrar para crear controladores de eventos en tiempo de ejecución para formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4bf81-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="4bf81-103">Además de crear eventos mediante Diseñador de Windows Forms, también puede crear un controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bf81-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="4bf81-104">Esta acción le permite conectar controladores de eventos basándose en las condiciones del código en tiempo de ejecución en lugar de conectarlos cuando se inicia el programa.</span><span class="sxs-lookup"><span data-stu-id="4bf81-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="4bf81-105">Para crear un controlador de eventos en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4bf81-105">To create an event handler at run time</span></span>  
  
1.  <span data-ttu-id="4bf81-106">Abra el formulario en el editor de código al que desee agregar un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="4bf81-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2.  <span data-ttu-id="4bf81-107">Agregue un método al formulario con la firma del método para el evento que desee controlar.</span><span class="sxs-lookup"><span data-stu-id="4bf81-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="4bf81-108">Por ejemplo, si desea controlar la <xref:System.Windows.Forms.Control.Click> eventos de un <xref:System.Windows.Forms.Button> control, debe crear un método como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bf81-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
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
  
3.  <span data-ttu-id="4bf81-109">Agregue el código al controlador de eventos según corresponda a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bf81-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4.  <span data-ttu-id="4bf81-110">Determine el formulario o control para el que desea crear un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="4bf81-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5.  <span data-ttu-id="4bf81-111">En un método de la clase del formulario, agregue código que especifique el controlador de eventos para controlar el evento.</span><span class="sxs-lookup"><span data-stu-id="4bf81-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="4bf81-112">Por ejemplo, el código siguiente especifica el controlador de eventos `button1_Click` controla la <xref:System.Windows.Forms.Control.Click> eventos de un <xref:System.Windows.Forms.Button> control:</span><span class="sxs-lookup"><span data-stu-id="4bf81-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="4bf81-113">El <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> método mostrado en el código de Visual Basic anterior establece un controlador de eventos click del botón.</span><span class="sxs-lookup"><span data-stu-id="4bf81-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf81-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bf81-114">See also</span></span>

- [<span data-ttu-id="4bf81-115">Crear controladores de eventos en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4bf81-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="4bf81-116">Información general sobre controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="4bf81-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="4bf81-117">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bf81-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
