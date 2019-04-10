---
title: Filtrar para obtener acceso a Document Object Model HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 04d5f9e6f128d9b4ed3f07a5faebe06ae4ffdebf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315197"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a>Filtrar para obtener acceso a Document Object Model HTML administrado
Puede acceder al Document Object Model (DOM) HTML administrado desde dos tipos de aplicaciones:  
  
-   Una aplicación de A Windows Forms (.exe) que hospedó el control <xref:System.Windows.Forms.WebBrowser> administrado. Estas dos tecnologías se complementan entre sí; el control <xref:System.Windows.Forms.WebBrowser> muestra la página al usuario y el DOM HTML representa la estructura lógica del documento.  
  
-   Un <xref:System.Windows.Forms.UserControl> de Windows Forms hospedado en Internet Explorer. Puede acceder al DOM HTML representando la página en la que su <xref:System.Windows.Forms.UserControl> está hospedado para cambiar la estructura del documento o abrir cuadros de diálogo modales, entre otras posibilidades.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>Para acceder al DOM desde una aplicación de Windows Forms  
  
1. Hospede un control <xref:System.Windows.Forms.WebBrowser> en su aplicación de Windows Forms y supervise el evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>. Para obtener información detallada sobre cómo hospedar controles y supervisar eventos, consulte [Eventos](../../../standard/events/index.md).  
  
2. Recupere el <xref:System.Windows.Forms.HtmlDocument> de la página actual; para ello, acceda a la propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A> del control <xref:System.Windows.Forms.WebBrowser>.  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>Para acceder al DOM desde un UserControl hospedado en Internet Explorer  
  
1. Cree su propia clase derivada personalizada de la clase <xref:System.Windows.Forms.UserControl>. Para obtener más información, vea [Cómo: Crear controles compuestos](how-to-author-composite-controls.md).  
  
2. Coloque el código siguiente dentro del controlador de evento Load para su <xref:System.Windows.Forms.UserControl>:  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
  
1. Cuando use DOM en el control <xref:System.Windows.Forms.WebBrowser>, debe esperar siempre hasta que se produzca el evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> antes de intentar acceder a la propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A> del control <xref:System.Windows.Forms.WebBrowser>. El evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> se genera una vez cargado todo el documento; si usa el DOM antes, corre el riesgo de provocar una excepción en tiempo de ejecución en su aplicación.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
  
1. Su aplicación o <xref:System.Windows.Forms.UserControl> requerirá confianza completa para poder acceder al DOM HTML administrado. Si está implementando una aplicación de Windows Forms mediante [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], puede solicitar confianza completa usando la elevación de permisos o una implementación de aplicación de confianza; consulte [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications) para obtener más información.  
  
## <a name="see-also"></a>Vea también

- [Utilizar el Modelo de objetos de documento HTML administrado](using-the-managed-html-document-object-model.md)
