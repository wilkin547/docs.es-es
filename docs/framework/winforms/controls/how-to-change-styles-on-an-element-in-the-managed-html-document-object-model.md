---
title: "C&#243;mo: Cambiar los estilos de un elemento en el Modelo de objetos de documento HTML administrado | Microsoft Docs"
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
  - "DOM HTML administrado, cambiar el estilo de los elementos"
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Cambiar los estilos de un elemento en el Modelo de objetos de documento HTML administrado
Puede utilizar estilos en HTML para controlar el aspecto de un documento y sus elementos.  <xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> admiten propiedades <xref:System.Windows.Forms.HtmlElement.Style%2A> que utilizan cadenas de estilo con el siguiente formato:  
  
 `name1:value1;...;nameN:valueN;`  
  
 A continuación, se muestra un `DIV` con una cadena de estilo que establece la fuente en Arial y todo el texto en negrita:  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 El problema de manipular estilos utilizando la propiedad <xref:System.Windows.Forms.HtmlElement.Style%2A> es que se puede probar la configuración para quitar valores de configuración de estilo individuales de una cadena o agregárselos.  Por ejemplo, sería un procedimiento complejo si tuviera que representar el texto anterior en cursiva siempre que el usuario sitúe el cursor sobre `DIV` y quite la cursiva cuando el cursor deje `DIV`.  El tiempo se convertiría en un problema si necesita manipular un número grande de estilos de esta manera.  
  
 El procedimiento siguiente contiene código que puede utilizar para manipular con facilidad los estilos en los elementos y documentos HTML.  El procedimiento requiere que sepa cómo realizar tareas básicas en formularios Windows Forms, tales como crear un nuevo proyecto y agregar un control al formulario.  
  
### Para procesar los cambios de estilo en una aplicación de Windows Forms  
  
1.  Cree un nuevo proyecto de formularios Windows Forms.  
  
2.  Cree un nuevo archivo de clase con una extensión adecuada para su lenguaje de programación.  
  
3.  Copie el código de clase `StyleGenerator` en la sección Ejemplo de este tema en el archivo de clase y guarde el código.  
  
4.  Guarde el HTML siguiente a un archivo denominado Test.htm.  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  Agregue un control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1` al formulario principal de su proyecto.  
  
6.  Agregue el siguiente al código al archivo de código del proyecto.  
  
    > [!IMPORTANT]
    >  Asegúrese de que el controlador del evento `webBrowser1_DocumentCompleted` está configurado como un agente de escucha para el evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.  En [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], haga doble clic en el control <xref:System.Windows.Forms.WebBrowser>; en un editor de texto, configure el agente de escucha mediante programación.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  Ejecute el proyecto.  Ejecute el cursor sobre el primer `DIV` para observar los efectos del código.  
  
## Ejemplo  
 El siguiente código de ejemplo muestra el código completo para la clase `StyleGenerator`, que analiza un valor de estilo existente, es compatible con la inclusión, modificación y eliminación de estilos, y devuelve un nuevo estilo con los cambios solicitados.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Forms.HtmlElement>