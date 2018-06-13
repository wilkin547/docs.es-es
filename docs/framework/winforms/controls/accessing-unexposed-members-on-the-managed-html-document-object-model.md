---
title: Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: d2fbccfb3ecd7716420ca951e86f728798d25258
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526438"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado
Administrado HTML Document Object Model (DOM) contiene una clase denominada <xref:System.Windows.Forms.HtmlElement> que expone las propiedades, métodos y eventos que todos los elementos HTML tienen en común. A veces, sin embargo, debe tener acceso a miembros que la interfaz administrada no expone directamente. En este tema se describen dos formas para tener acceso a miembros no expuestos, incluidos [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] y las funciones de VBScript definidas dentro de una página Web.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Obtener acceso a miembros no expuestos a través de Interfaces administradas  
 <xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> proporcionan cuatro métodos que permiten el acceso a miembros no expuestos. La tabla siguiente muestran los tipos y sus métodos correspondientes.  
  
|Tipo de miembro|Métodos|  
|-----------------|-----------------|  
|Propiedades (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Métodos|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Al usar estos métodos, se supone que tiene un elemento del tipo subyacente correcto. Suponga que desea escuchar la `Submit` eventos de un `FORM` página de elemento de HTML, por lo que puede realizar algún procesamiento previo en el `FORM`de valores antes de que el usuario los envíe al servidor. Lo ideal es que, si tiene control sobre el código HTML, tendría que definir la `FORM` tener un único `ID` atributo.  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 Después de cargar esta página en el <xref:System.Windows.Forms.WebBrowser> control, que se puede utilizar el <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> método para recuperar el `FORM` en tiempo de ejecución mediante `form1` como argumento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Obtener acceso a las Interfaces no administradas  
 También puede tener acceso a miembros no expuestos en el DOM HTML administrado mediante el uso de las interfaces no administradas de modelo de objetos componentes (COM) expuestas por cada clase de DOM. Esto se recomienda si tiene que realizar varias llamadas a miembros no expuestos, o si los miembros no expuestos devuelven otras interfaces no administradas no contenidas en el DOM. HTML administrado  
  
 La tabla siguiente muestran todas las interfaces no administradas que se exponen a través de DOM. HTML administrado Haga clic en cada vínculo para obtener una explicación de su uso y, por ejemplo, el código.  
  
|Tipo|Interfaz no administrada|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 La manera más fácil de usar las interfaces COM es agregar una referencia a la biblioteca no administrada de DOM HTML (MSHTML.dll) desde su aplicación, aunque esto no se admite. Para obtener más información, consulte [934368 de artículo de Knowledge Base](http://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Obtener acceso a las funciones del Script  
 Una página HTML puede definir una o más funciones utilizando un lenguaje de scripting como [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript. Estas funciones se colocan dentro de un `SCRIPT` página de la página y puede ejecutar a petición o en respuesta a un evento en el DOM.  
  
 Se pueden llamar a las funciones de script se define en una página HTML mediante el <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> método. Si el método de script devuelve un elemento HTML, puede usar una conversión para convertir este resultado devuelto para un <xref:System.Windows.Forms.HtmlElement>. Para obtener más información y código de ejemplo, vea <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar el Modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
