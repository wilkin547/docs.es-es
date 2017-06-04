---
title: "C&#243;mo: Obtener acceso al Modelo de objetos de documento HTML administrado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DOM de HTML, obtener acceso"
  - "administra el DOM de HTML, obtener acceso"
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Obtener acceso al Modelo de objetos de documento HTML administrado
Puede acceder al Document Object Model (DOM) HTML administrado desde dos tipos de aplicaciones:  
  
-   Una aplicación de Windows Forms (.exe) que hospeda los recursos administrados <xref:System.Windows.Forms.WebBrowser> control. Estas dos tecnologías complementan entre sí, con el <xref:System.Windows.Forms.WebBrowser> control que muestra la página al usuario y el DOM HTML representa la estructura lógica del documento.  
  
-   Formularios Windows Forms <xref:System.Windows.Forms.UserControl> hospedado en Internet Explorer. Se puede acceder al DOM de HTML que representa la página en la que su <xref:System.Windows.Forms.UserControl> está hospedado para cambiar la estructura del documento o abrir cuadros de diálogo modales, entre otras posibilidades.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>Para acceder al DOM desde una aplicación de Windows Forms  
  
1.  Host de un <xref:System.Windows.Forms.WebBrowser> control dentro de la aplicación de formularios Windows Forms y supervise el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos. Para obtener detalles en hospedar controles y supervisar los eventos, vea [eventos](../../../../docs/standard/events/index.md).  
  
2.  Recuperar el <xref:System.Windows.Forms.HtmlDocument> para la página actual mediante el acceso a la <xref:System.Windows.Forms.WebBrowser.Document%2A> propiedad de la <xref:System.Windows.Forms.WebBrowser> control.  
  
<!-- TODO: review snippet reference  [!CODE [AccessHTMLDOMApp#1](AccessHTMLDOMApp#1)]  -->  
  
### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>Para acceder al DOM desde un UserControl hospedado en Internet Explorer  
  
1.  Crear su propia clase personalizada derivada de la <xref:System.Windows.Forms.UserControl> clase. Para obtener más información, consulte [Cómo: crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).  
  
2.  Coloque el código siguiente dentro del controlador de eventos de carga para su <xref:System.Windows.Forms.UserControl>:  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
  
1.  Cuando utiliza el DOM mediante el <xref:System.Windows.Forms.WebBrowser> control, siempre debe esperar hasta que el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento se produce antes de intentar tener acceso a la <xref:System.Windows.Forms.WebBrowser.Document%2A> propiedad de la <xref:System.Windows.Forms.WebBrowser> control. El <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento se genera cuando se haya cargado todo el documento; si usa el DOM antes, se arriesga a provocar una excepción de tiempo de ejecución de la aplicación.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
  
1.  La aplicación o <xref:System.Windows.Forms.UserControl> requerirá plena confianza para poder acceder administrado HTML DOM. Si va a implementar una aplicación de formularios Windows Forms con [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], puede solicitar la plena confianza mediante elevación de permisos o implementación de aplicaciones de confianza; vea [proteger las aplicaciones ClickOnce](../Topic/Securing%20ClickOnce%20Applications.md) para obtener más información.  
  
## <a name="see-also"></a>Vea también  
 [Con el modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)