---
title: 'Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 1330e20cc4fe7df86e51bebca28e4a71e3108673
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530548"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms
Puede usar el <xref:System.Windows.Forms.WebBrowser> control para mostrar e imprimir documentos HTML sin proporcionar la funcionalidad completa de un explorador Web de Internet. Esto es útil cuando desea aprovechar las ventajas de las funciones de formato de HTML pero no desea que los usuarios carguen arbitraria páginas Web que pueden contener controles Web no es de confianza o código de script posiblemente malintencionado. Es posible que desee restringir la capacidad de la <xref:System.Windows.Forms.WebBrowser> de control de esta manera, por ejemplo, para utilizarlo como un visor de correo electrónico HTML o para proporcionar ayuda con formato HTML en la aplicación.  
  
### <a name="to-create-an-html-document-viewer"></a>Para crear un visor de documentos HTML  
  
1.  Establecer el <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> propiedad `false` para evitar la <xref:System.Windows.Forms.WebBrowser> control abra los archivos colocados en él.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  Establecer el <xref:System.Windows.Forms.WebBrowser.Url%2A> propiedad a la ubicación del archivo inicial que se va a mostrar.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.  
  
-   Referencias a los ensamblados `System` y `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [Información general sobre el control WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [Seguridad de WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [Desplazarse a una dirección URL con el control WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
