---
title: 'Cómo: Consumir eventos en una aplicación de formularios Web Forms'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
ms.openlocfilehash: 1f95fd0dcc12f2d4e47ee07e1e6bb15d91000f0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124781"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="0afa0-102">Cómo: Consumir eventos en una aplicación de formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="0afa0-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="0afa0-103">Un escenario común de las aplicaciones de Web Forms de ASP.NET es rellenar una página web que controla y realiza una acción específica basada en qué control hace clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="0afa0-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="0afa0-104">Por ejemplo, un control <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> genera un evento cuando el usuario hace clic en él en la página web.</span><span class="sxs-lookup"><span data-stu-id="0afa0-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="0afa0-105">Mediante el control del evento, la aplicación puede ejecutar la lógica de aplicación apropiada para ese clic de botón.</span><span class="sxs-lookup"><span data-stu-id="0afa0-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="0afa0-106">Para controlar un evento de clic de botón en una página web</span><span class="sxs-lookup"><span data-stu-id="0afa0-106">To handle a button click event on a webpage</span></span>  
  
1. <span data-ttu-id="0afa0-107">Cree una página (página web) de Web Forms de ASP.NET que tenga un control <xref:System.Web.UI.WebControls.Button> con el valor `OnClick` establecido en el nombre del método que va a definir en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="0afa0-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. <span data-ttu-id="0afa0-108">Defina un controlador de eventos que coincida con la firma de delegado de eventos <xref:System.Web.UI.WebControls.Button.Click> y que tenga el nombre definido para el valor `OnClick`.</span><span class="sxs-lookup"><span data-stu-id="0afa0-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     <span data-ttu-id="0afa0-109">El evento <xref:System.Web.UI.WebControls.Button.Click> usa la clase <xref:System.EventHandler> para el tipo delegado y la clase <xref:System.EventArgs> para los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="0afa0-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="0afa0-110">El marco de trabajo de la página de ASP.NET genera automáticamente el código que crea una instancia de <xref:System.EventHandler> y agrega esta instancia de delegado al evento <xref:System.Web.UI.WebControls.Button.Click> de la instancia <xref:System.Web.UI.WebControls.Button>.</span><span class="sxs-lookup"><span data-stu-id="0afa0-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3. <span data-ttu-id="0afa0-111">En el método del controlador de eventos definido en el paso 2, agregue código para realizar las acciones necesarias cuando se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="0afa0-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0afa0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0afa0-112">See also</span></span>

- [<span data-ttu-id="0afa0-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="0afa0-113">Events</span></span>](../../../docs/standard/events/index.md)
