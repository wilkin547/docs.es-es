---
title: Acceso a marcos en el Modelo de objetos de documento HTML administrado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9355596982025bf9834924a0de8e79e7073fc0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a>Acceso a marcos en el Modelo de objetos de documento HTML administrado
Algunos documentos HTML están compuestos de *fotogramas*, o ventanas que pueden contener sus propios documentos HTML distintos. Los marcos facilitan la creación de páginas HTML porque permiten que una o más partes de la página permanezcan estáticas, como una barra de navegación, mientras que otros marcos cambian su contenido constantemente.  
  
 Los autores de HTML pueden crear los marcos de una de dos maneras:  
  
-   Con etiquetas `FRAMESET` y `FRAME`, que crea ventanas fijas.  
  
 O bien  
  
-   Con la etiqueta `IFRAME`, que crea una ventana flotante que puede cambiar de posición en tiempo de ejecución.  
  
1.  Como los marcos contienen documentos HTML, se representan en el modelo de objetos de documento (DOM) como elementos de ventana y elementos de marco.  
  
2.  Al acceder a una etiqueta `FRAME` o `IFRAME` mediante la colección Frames de <xref:System.Windows.Forms.HtmlWindow>, se recupera el elemento de ventana correspondiente al marco. Esto representa todas las propiedades dinámicas del marco, como su dirección URL, documento y tamaño actual.  
  
3.  Al acceder a una etiqueta `FRAME` o `IFRAME` mediante la propiedad <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> de <xref:System.Windows.Forms.HtmlWindow>, la colección <xref:System.Windows.Forms.HtmlElement.Children%2A> o métodos como <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> o <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, se recupera el elemento de marco. Esto representa las propiedades estáticas del marco, incluida la dirección URL especificada en el archivo HTML original.  
  
## <a name="frames-and-security"></a>Marcos y seguridad  
 Obtener acceso a los marcos es complicado por el hecho de que el DOM HTML administrado implementa una medida de seguridad que se conoce como *seguridad scripting entre marcos*. Si un documento contiene un `FRAMESET` con dos o más `FRAME` en dominios diferentes, estos `FRAME` no pueden interactuar entre sí. En otras palabras, un `FRAME` que muestra el contenido del sitio web no puede acceder a la información de un `FRAME` que hospeda un sitio de terceros, como http://www.adatum.com/. Esta seguridad se implementa en el nivel de la clase <xref:System.Windows.Forms.HtmlWindow>. Puede obtener información general sobre un `FRAME` que hospeda otro sitio web, como su dirección URL, pero no podrá acceder a su <xref:System.Windows.Forms.HtmlWindow.Document%2A> ni cambiar el tamaño o la ubicación de su `FRAME` o `IFRAME` host.  
  
 Esta regla también se aplica a las ventanas que se abren con los métodos <xref:System.Windows.Forms.HtmlWindow.Open%2A> y <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A>. Si la ventana que abre está en un dominio distinto de la página hospedada en el control <xref:System.Windows.Forms.WebBrowser>, no podrá mover esa ventana ni examinar su contenido. Estas restricciones también se aplican si usa el control <xref:System.Windows.Forms.WebBrowser> para mostrar un sitio web distinto del sitio web usado para implementar su aplicación de Windows Forms. Si usa la tecnología de implementación de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] para instalar la aplicación desde el sitio web A y usar el <xref:System.Windows.Forms.WebBrowser> para mostrar el sitio web B, no podrá acceder a los datos del sitio web B.  
  
 Para obtener más información acerca del scripting entre sitios, consulte[sobre Scripting entre marcos y seguridad](http://msdn.microsoft.com/library/ms533028.aspx).  
  
## <a name="see-also"></a>Vea también  
 [Elemento de marco &#124; Objeto Frame](http://msdn.microsoft.com/library/ms535250.aspx)  
 [Utilizar el Modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
