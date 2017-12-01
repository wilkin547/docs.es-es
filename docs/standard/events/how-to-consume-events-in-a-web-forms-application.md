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
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Cómo: Consumir eventos en una aplicación de formularios Web Forms
Es un escenario común en las aplicaciones de formularios Web Forms de ASP.NET rellenar una página Web con controles y, a continuación, realizar una acción concreta basada en el control que el usuario hace clic. Por ejemplo, un <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control provoca un evento cuando el usuario hace clic en él en la página Web. Controlando el evento, la aplicación puede realizar la lógica de aplicación adecuada para ese clic del botón.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Para controlar un evento de clic de botón en una página web  
  
1.  Crear una página de formularios Web Forms de ASP.NET (página Web) que tiene un <xref:System.Web.UI.WebControls.Button> controlar con el `OnClick` valor establecido en el nombre del método que va a definir en el paso siguiente.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Definir un controlador de eventos que coincida con el <xref:System.Web.UI.WebControls.Button.Click> firma de delegado de evento y que tiene el nombre definido para el `OnClick` valor.  
  
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
  
     El <xref:System.Web.UI.WebControls.Button.Click> evento utiliza el <xref:System.EventHandler> clase para el tipo de delegado y la <xref:System.EventArgs> clase para los datos del evento. El marco de trabajo de la página ASP.NET genera automáticamente el código que crea una instancia de <xref:System.EventHandler> y agrega esta instancia de delegado a la <xref:System.Web.UI.WebControls.Button.Click> eventos de la <xref:System.Web.UI.WebControls.Button> instancia.  
  
3.  En el evento método del controlador que define en el paso 2, agregue código para realizar las acciones necesarias cuando se produce el evento.  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../docs/standard/events/index.md)
