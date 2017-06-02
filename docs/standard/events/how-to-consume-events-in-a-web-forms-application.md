---
title: "C&#243;mo: Consumir eventos en una aplicaci&#243;n de formularios Web Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "eventos [.NET Framework], formularios Web Forms"
  - "controles de formularios Web Forms y eventos"
  - "controladores de eventos [.NET Framework], formularios Web Forms"
  - "eventos [.NET Framework], consumir"
  - "formularios Web Forms, control de eventos"
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# C&#243;mo: Consumir eventos en una aplicaci&#243;n de formularios Web Forms
Un escenario común en las aplicaciones de formularios web forms de ASP.NET es rellenar una página Web con controles, y después realizar una acción concreta basada en qué hace clic el usuario.  Por ejemplo, un control de <xref:System.Web.UI.WebControls.Button?displayProperty=fullName> provoca un evento cuando el usuario hace clic en la página Web.  Controlando el evento, la aplicación puede ejecutar la lógica de aplicación adecuada para ese clic del botón.  
  
### Para controlar un evento de clic de botón en una página web  
  
1.  Cree una página de formularios web forms ASP.NET \(página Web\) que tiene un control de <xref:System.Web.UI.WebControls.Button> con el valor de `OnClick` establecido en el nombre de método que definirá en el paso siguiente.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Defina un controlador de eventos que coincida con la firma de delegado del evento de <xref:System.Web.UI.WebControls.Button.Click> y que tiene el nombre definió por el valor de `OnClick` .  
  
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
  
     El evento <xref:System.Web.UI.WebControls.Button.Click> usa la clase <xref:System.EventHandler> para el tipo de delegado y la clase <xref:System.EventArgs> para los datos del evento.  El marco de trabajo de páginas ASP.NET genera automáticamente el código que crea una instancia de <xref:System.EventHandler> y agrega esta instancia del delegado al evento de <xref:System.Web.UI.WebControls.Button.Click> de la instancia de <xref:System.Web.UI.WebControls.Button> .  
  
3.  En el método de control de eventos que definió en el paso 2, agregue código para realizar cualquier acción necesaria cuando el evento.  
  
## Vea también  
 [Eventos](../../../docs/standard/events/index.md)