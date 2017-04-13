---
title: "Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DOM HTML administrado, obtener acceso a miembros no expuestos"
  - "miembros no expuestos"
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado
El Modelo de objeto del documento HTML \(DOM\) contiene una clase denominada <xref:System.Windows.Forms.HtmlElement> que expone las propiedades, método y eventos que todos los elementos HTML tienen en común.  Sin embargo, a veces necesitará obtener acceso a miembros que la interfaz administrada no expone directamente.  En este tema se describen dos formas de obtener acceso a los miembros no expuestos, incluidas las funciones de [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] y VBScript definidas dentro de una página web.  
  
## Acceso a miembros no expuestos a través de interfaces administradas  
 <xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> proporcionan cuatro métodos que permiten el acceso a los miembros no expuestos.  La tabla siguiente muestra los tipos y sus métodos correspondientes.  
  
|Tipo de miembro|Método\(s\)|  
|---------------------|-----------------|  
|Propiedades \(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Métodos|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventos \(<xref:System.Windows.Forms.HtmlDocument>\)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventos \(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventos \(<xref:System.Windows.Forms.HtmlWindow>\)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Cuando utiliza estos métodos, se supone que tiene un elemento del tipo subyacente correcto.  Suponga que desea escuchar al evento `Submit` de un elemento `FORM` en una página HTML, de modo que pueda realizar el preprocesamiento en los valores del `FORM` antes de que el usuario los envíe al servidor.  La situación ideal es que si tiene el control sobre el código HTML, defina el `FORM` para tener un atributo `ID` único.  
  
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
  
 Después de cargar esta página en el control <xref:System.Windows.Forms.WebBrowser>, puede utilizar el método <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> para recuperar el `FORM` en tiempo de ejecución utilizando `form1` como argumento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## Obtener acceso a las interfaces no administradas  
 También puede obtener acceso a miembros no expuestos del DOM HTML utilizando las interfaces no administradas del Modelo de objetos componentes \(COM\) expuestas por cada clase de DOM.  Es recomendable si debe realizar varias llamadas a miembros no expuestos o si estos miembros devuelven otras interfaces no administradas no contenidas en el DOM HTML administrado.  
  
 La tabla siguiente muestra todas las interfaces no administradas expuestas a través del DOM HTML administrado.  Haga clic en cada vínculo para obtener una explicación de su uso y un ejemplo de código.  
  
|Tipo|Interfaz no administrada|  
|----------|------------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 La manera más fácil de utilizar las interfaces COM es agregar una referencia a la biblioteca DOM HTML \(MSHTML.dll\) de la aplicación, aunque esto se no compatible.  Para obtener más información, vea [artículo 934368 de Knowledge Base](http://support.microsoft.com/kb/934368).  
  
## Obtener acceso a las funciones de script  
 Una página HTML puede definir una o más funciones utilizando un lenguaje de scripting como [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript.  Estas funciones se incluyen en una página de `SCRIPT` en la página y se pueden ejecutar a petición o como respuesta a un evento del DOM.  
  
 Puede llamar a cualquiera de las funciones de script que defina en una página HTML usando el método <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  Si el método de script devuelve un elemento HTML, puede utilizar una conversión de tipos para convertir este resultado devuelto en una <xref:System.Windows.Forms.HtmlElement>.  Para obtener información detallada y código de ejemplo, vea <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## Vea también  
 [Utilizar el Modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)