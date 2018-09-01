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
ms.openlocfilehash: 8767ef0fb484d43ffad4888affebb9d6bb74cc3a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384645"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado
Administrado HTML Document Object Model (DOM) contiene una clase denominada <xref:System.Windows.Forms.HtmlElement> que expone las propiedades, métodos y eventos que sean comunes a todos los elementos HTML. A veces, sin embargo, necesitará tener acceso a miembros que no exponen directamente a la interfaz administrada. En este tema se describen dos formas para tener acceso a miembros no expuestos, así como [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] y funciones de VBScript definidas dentro de una página Web.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Acceso a miembros no expuestos a través de Interfaces administradas  
 <xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> proporcionan cuatro métodos que permiten el acceso a miembros no expuestos. En la tabla siguiente se muestra los tipos y sus métodos correspondientes.  
  
|Tipo de miembro|Método (s)|  
|-----------------|-----------------|  
|Propiedades (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Métodos|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Al usar estos métodos, se supone que tiene un elemento del tipo subyacente correcto. Suponga que desea escuchar el `Submit` eventos de un `FORM` página de elemento en un elemento HTML, por lo que puede realizar algún procesamiento previo en el `FORM`de valores antes de que el usuario los envíe al servidor. Lo ideal es que, si tiene control sobre la HTML, definiría la `FORM` para tener un único `ID` atributo.  
  
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
  
 Después de cargar esta página en el <xref:System.Windows.Forms.WebBrowser> control, puede usar el <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> método para recuperar el `FORM` en tiempo de ejecución mediante `form1` como argumento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Obtener acceso a las Interfaces no administradas  
 También puede tener acceso a miembros no expuestos en el DOM HTML administrado mediante el uso de las interfaces no administradas de modelo de objetos componentes (COM) expuestas por cada clase de DOM. Esto se recomienda si tiene que realizar varias llamadas a miembros no expuestos, o si estos miembros devuelven otras interfaces no administradas no encapsuladas por administrado HTML DOM.  
  
 La tabla siguiente muestran todas las interfaces no administradas que se exponen a través de HTML DOM. administrado Haga clic en cada vínculo para obtener una explicación de su uso y, por ejemplo, el código.  
  
|Tipo|Interfaz no administrada|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 La manera más fácil de usar las interfaces COM es agregar una referencia a la biblioteca no administrada de DOM de HTML (MSHTML.dll) desde su aplicación, aunque esto no se admite. Para obtener más información, consulte [934368 del artículo de Knowledge Base](https://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Obtener acceso a las funciones de Script  
 Una página HTML puede definir una o varias funciones mediante un lenguaje de scripting, como [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript. Estas funciones se colocan dentro de un `SCRIPT` página en la página y se pueden ejecutar a petición o en respuesta a un evento en el DOM.  
  
 Puede llamar a cualquier funciones de secuencia de comandos que se definen en una página HTML mediante la <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> método. Si el método de script devuelve un elemento HTML, puede usar una conversión de tipos para convertir este resultado devuelto para un <xref:System.Windows.Forms.HtmlElement>. Para obtener información detallada y código de ejemplo, vea <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar el Modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
