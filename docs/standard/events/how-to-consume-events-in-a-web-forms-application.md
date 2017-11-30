---
title: "Cómo: Consumir eventos en una aplicación de formularios Web Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bdb0a6be309f27348ba13bf93fd5aedd3c66a792
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="75623-102">Cómo: Consumir eventos en una aplicación de formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="75623-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="75623-103">Es un escenario común en las aplicaciones de formularios Web Forms de ASP.NET rellenar una página Web con controles y, a continuación, realizar una acción concreta basada en el control que el usuario hace clic.</span><span class="sxs-lookup"><span data-stu-id="75623-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="75623-104">Por ejemplo, un <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control provoca un evento cuando el usuario hace clic en él en la página Web.</span><span class="sxs-lookup"><span data-stu-id="75623-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="75623-105">Controlando el evento, la aplicación puede realizar la lógica de aplicación adecuada para ese clic del botón.</span><span class="sxs-lookup"><span data-stu-id="75623-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="75623-106">Para controlar un evento de clic de botón en una página web</span><span class="sxs-lookup"><span data-stu-id="75623-106">To handle a button click event on a webpage</span></span>  
  
1.  <span data-ttu-id="75623-107">Crear una página de formularios Web Forms de ASP.NET (página Web) que tiene un <xref:System.Web.UI.WebControls.Button> controlar con el `OnClick` valor establecido en el nombre del método que va a definir en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="75623-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  <span data-ttu-id="75623-108">Definir un controlador de eventos que coincida con el <xref:System.Web.UI.WebControls.Button.Click> firma de delegado de evento y que tiene el nombre definido para el `OnClick` valor.</span><span class="sxs-lookup"><span data-stu-id="75623-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
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
  
     <span data-ttu-id="75623-109">El <xref:System.Web.UI.WebControls.Button.Click> evento utiliza el <xref:System.EventHandler> clase para el tipo de delegado y la <xref:System.EventArgs> clase para los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="75623-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="75623-110">El marco de trabajo de la página ASP.NET genera automáticamente el código que crea una instancia de <xref:System.EventHandler> y agrega esta instancia de delegado a la <xref:System.Web.UI.WebControls.Button.Click> eventos de la <xref:System.Web.UI.WebControls.Button> instancia.</span><span class="sxs-lookup"><span data-stu-id="75623-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3.  <span data-ttu-id="75623-111">En el evento método del controlador que define en el paso 2, agregue código para realizar las acciones necesarias cuando se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="75623-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75623-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="75623-112">See Also</span></span>  
 [<span data-ttu-id="75623-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="75623-113">Events</span></span>](../../../docs/standard/events/index.md)
