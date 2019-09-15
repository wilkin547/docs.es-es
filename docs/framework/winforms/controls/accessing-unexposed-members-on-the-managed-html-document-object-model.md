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
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988400"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado
El Document Object Model HTML administrado (dom) contiene una clase denominada <xref:System.Windows.Forms.HtmlElement> que expone las propiedades, los métodos y los eventos que tienen todos los elementos HTML en común. Sin embargo, a veces necesitará tener acceso a los miembros que la interfaz administrada no expone directamente. En este tema se examinan dos formas de obtener acceso a miembros no expuestos, incluidas las funciones de JScript y VBScript definidas dentro de una página web.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Obtener acceso a miembros no expuestos a través de interfaces administradas  
 <xref:System.Windows.Forms.HtmlDocument>y <xref:System.Windows.Forms.HtmlElement> proporcionan cuatro métodos que permiten el acceso a miembros no expuestos. En la tabla siguiente se muestran los tipos y sus métodos correspondientes.  
  
|Tipo de miembro|Método (s)|  
|-----------------|-----------------|  
|Propiedades (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Métodos|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventos (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Cuando se usan estos métodos, se supone que tiene un elemento del tipo subyacente correcto. Supongamos que desea escuchar el `Submit` evento de un `FORM` elemento en una página HTML, de modo que pueda realizar algún procesamiento previo de los `FORM`valores de antes de que el usuario los envíe al servidor. Idealmente, si tiene control sobre el código HTML, definiría `FORM` para tener un atributo único. `ID`  
  
```html  
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
  
 Después de cargar esta página en el <xref:System.Windows.Forms.WebBrowser> control, puede usar el <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> método para recuperar `FORM` en tiempo de ejecución utilizando `form1` como argumento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Acceso a interfaces no administradas  
 También puede tener acceso a miembros no expuestos en el DOM HTML administrado mediante las interfaces del modelo de objetos componentes (COM) no administradas expuestas por cada clase DOM. Esto se recomienda si tiene que realizar varias llamadas a miembros no expuestos, o si los miembros no expuestos devuelven otras interfaces no administradas no encapsuladas por el DOM HTML administrado.  
  
 En la tabla siguiente se muestran todas las interfaces no administradas que se exponen a través del DOM HTML administrado. Haga clic en cada vínculo para obtener una explicación de su uso y el código de ejemplo.  
  
|Type|Interfaz no administrada|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 La manera más sencilla de utilizar las interfaces COM es agregar una referencia a la biblioteca DOM HTML no administrada (MSHTML. dll) de la aplicación, aunque no se admite. Para obtener más información, vea el [artículo 934368 de Knowledge Base](https://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Obtener acceso a funciones de script  
 Una página HTML puede definir una o varias funciones mediante un lenguaje de scripting como JScript o VBScript. Estas funciones se colocan dentro `SCRIPT` de una página de la página y se pueden ejecutar a petición o como respuesta a un evento en el Dom.  
  
 Puede llamar a cualquier función de script que defina en una página HTML mediante <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> el método. Si el método de script devuelve un elemento HTML, puede usar una conversión para convertir el resultado devuelto en <xref:System.Windows.Forms.HtmlElement>. Para obtener más información y código de <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>ejemplo, vea.  
  
## <a name="see-also"></a>Vea también

- [Utilizar el Modelo de objetos de documento HTML administrado](using-the-managed-html-document-object-model.md)
