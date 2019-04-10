---
title: Acceso a marcos en el Modelo de objetos de documento HTML administrado
ms.date: 03/30/2017
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
ms.openlocfilehash: 9b2719ca000ab86b9ca40f9e78af46cbf598d16e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337635"
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a>Acceso a marcos en el Modelo de objetos de documento HTML administrado
Algunos documentos HTML están compuestos de *marcos*, o windows que pueden contener sus propios documentos HTML distintos. Los marcos facilitan la creación de páginas HTML porque permiten que una o más partes de la página permanezcan estáticas, como una barra de navegación, mientras que otros marcos cambian su contenido constantemente.  
  
 Los autores de HTML pueden crear los marcos de una de dos maneras:  
  
-   Con etiquetas `FRAMESET` y `FRAME`, que crea ventanas fijas.  
  
 -o bien-  
  
-   Con la etiqueta `IFRAME`, que crea una ventana flotante que puede cambiar de posición en tiempo de ejecución.  
  
1. Como los marcos contienen documentos HTML, se representan en el modelo de objetos de documento (DOM) como elementos de ventana y elementos de marco.  
  
2. Al acceder a una etiqueta `FRAME` o `IFRAME` mediante la colección Frames de <xref:System.Windows.Forms.HtmlWindow>, se recupera el elemento de ventana correspondiente al marco. Esto representa todas las propiedades dinámicas del marco, como su dirección URL, documento y tamaño actual.  
  
3. Al acceder a una etiqueta `FRAME` o `IFRAME` mediante la propiedad <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> de <xref:System.Windows.Forms.HtmlWindow>, la colección <xref:System.Windows.Forms.HtmlElement.Children%2A> o métodos como <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> o <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, se recupera el elemento de marco. Esto representa las propiedades estáticas del marco, incluida la dirección URL especificada en el archivo HTML original.  
  
## <a name="frames-and-security"></a>Marcos y seguridad  
 Obtener acceso a los marcos es complicado por el hecho de que el DOM HTML administrado implementa una medida de seguridad conocido como *seguridad de scripting entre marcos*. Si un documento contiene un `FRAMESET` con dos o más `FRAME` en dominios diferentes, estos `FRAME` no pueden interactuar entre sí. En otras palabras, un `FRAME` que muestra el contenido del sitio Web no puede tener acceso a información en un `FRAME` que hospeda un sitio de terceros, como `http://www.adatum.com/`. Esta seguridad se implementa en el nivel de la clase <xref:System.Windows.Forms.HtmlWindow>. Puede obtener información general sobre un `FRAME` que hospeda otro sitio web, como su dirección URL, pero no podrá acceder a su <xref:System.Windows.Forms.HtmlWindow.Document%2A> ni cambiar el tamaño o la ubicación de su `FRAME` o `IFRAME` host.  
  
 Esta regla también se aplica a las ventanas que se abren con los métodos <xref:System.Windows.Forms.HtmlWindow.Open%2A> y <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A>. Si la ventana que abre está en un dominio distinto de la página hospedada en el control <xref:System.Windows.Forms.WebBrowser>, no podrá mover esa ventana ni examinar su contenido. Estas restricciones también se aplican si usa el control <xref:System.Windows.Forms.WebBrowser> para mostrar un sitio web distinto del sitio web usado para implementar su aplicación de Windows Forms. Si usa la tecnología de implementación de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] para instalar la aplicación desde el sitio web A y usar el <xref:System.Windows.Forms.WebBrowser> para mostrar el sitio web B, no podrá acceder a los datos del sitio web B.  
  
## <a name="see-also"></a>Vea también

- [\<marco > elemento](https://developer.mozilla.org/docs/Web/HTML/Element/frame)
- [Utilizar el Modelo de objetos de documento HTML administrado](using-the-managed-html-document-object-model.md)
