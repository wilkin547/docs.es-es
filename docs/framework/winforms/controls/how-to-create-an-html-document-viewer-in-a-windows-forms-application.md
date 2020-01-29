---
title: Crear un visor de documentos HTML en una aplicación Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732843"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms
Puede usar el control <xref:System.Windows.Forms.WebBrowser> para mostrar e imprimir documentos HTML sin proporcionar la funcionalidad completa de un explorador Web de Internet. Esto resulta útil si desea aprovechar las capacidades de formato de HTML pero no desea que los usuarios carguen páginas web arbitrarias que pueden contener controles Web que no son de confianza o código de script potencialmente malintencionado. Es posible que desee restringir la funcionalidad del control de <xref:System.Windows.Forms.WebBrowser> de esta manera, por ejemplo, para usarlo como un visor de correo electrónico HTML o para proporcionar ayuda con formato HTML en la aplicación.  
  
### <a name="to-create-an-html-document-viewer"></a>Para crear un visor de documentos HTML  
  
1. Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> Abra los archivos colocados en él.  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A> en la ubicación del archivo inicial que se va a mostrar.  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.  
  
- Referencias a los ensamblados `System` y `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [Información general sobre el control WebBrowser](webbrowser-control-overview.md)
- [Seguridad de WebBrowser](webbrowser-security.md)
- [Desplazarse a una dirección URL con el control WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md)
