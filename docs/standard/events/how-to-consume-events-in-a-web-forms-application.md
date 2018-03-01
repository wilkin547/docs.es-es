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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d0fec2ed34968bfa8c296f08739dec28e6a6eab9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Cómo: Consumir eventos en una aplicación de formularios Web Forms
Un escenario común de las aplicaciones de Web Forms de ASP.NET es rellenar una página web que controla y realiza una acción específica basada en qué control hace clic el usuario. Por ejemplo, un control <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> genera un evento cuando el usuario hace clic en él en la página web. Mediante el control del evento, la aplicación puede ejecutar la lógica de aplicación apropiada para ese clic de botón.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Para controlar un evento de clic de botón en una página web  
  
1.  Cree una página (página web) de Web Forms de ASP.NET que tenga un control <xref:System.Web.UI.WebControls.Button> con el valor `OnClick` establecido en el nombre del método que va a definir en el paso siguiente.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Defina un controlador de eventos que coincida con la firma de delegado de eventos <xref:System.Web.UI.WebControls.Button.Click> y que tenga el nombre definido para el valor `OnClick`.  
  
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
  
     El evento <xref:System.Web.UI.WebControls.Button.Click> usa la clase <xref:System.EventHandler> para el tipo delegado y la clase <xref:System.EventArgs> para los datos del evento. El marco de trabajo de la página de ASP.NET genera automáticamente el código que crea una instancia de <xref:System.EventHandler> y agrega esta instancia de delegado al evento <xref:System.Web.UI.WebControls.Button.Click> de la instancia <xref:System.Web.UI.WebControls.Button>.  
  
3.  En el método del controlador de eventos definido en el paso 2, agregue código para realizar las acciones necesarias cuando se produce el evento.  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../docs/standard/events/index.md)
