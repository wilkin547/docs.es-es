---
title: 'Cómo: Cambiar los estilos de un elemento en el Modelo de objetos de documento HTML administrado'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e833a15e33d0baf80f0078b26758137e7908a8fd
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Cómo: Cambiar los estilos de un elemento en el Modelo de objetos de documento HTML administrado
Puede utilizar estilos en HTML para controlar la apariencia de un documento y sus elementos. <xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> admite <xref:System.Windows.Forms.HtmlElement.Style%2A> propiedades que toman cadenas de estilo de los formatos siguientes:  
  
 `name1:value1;...;nameN:valueN;`  
  
 Este es un `DIV` con una cadena de estilo que establece la fuente Arial y todo el texto en negrita:  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 El problema de manipular estilos utilizando el <xref:System.Windows.Forms.HtmlElement.Style%2A> propiedad es que puede resultar tedioso para agregar y quitar la configuración de estilo individuales de la cadena. Por ejemplo, se podría convertir en un procedimiento complejo para que pueda representar el texto anterior en cursiva siempre que el usuario coloca el cursor sobre la `DIV`y quite la cursiva desactivada cuando el cursor sale la `DIV`. Tiempo se convertiría en un problema si es necesario manipular un gran número de estilos de esta manera.  
  
 El procedimiento siguiente contiene código que puede usar para manipular fácilmente estilos en documentos HTML y los elementos. El procedimiento requiere que sepa cómo realizar tareas básicas en formularios Windows Forms, como crear un nuevo proyecto y agregar un control a un formulario.  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Para procesar los cambios de estilo en una aplicación de formularios Windows Forms  
  
1.  Cree un nuevo proyecto de Windows Forms.  
  
2.  Crear un nuevo archivo de clase termina en extensión adecuada para su lenguaje de programación.  
  
3.  Copia la `StyleGenerator` código en la sección de ejemplo de este tema de la clase en el archivo de clase y guarde el código.  
  
4.  Guarde el siguiente código HTML en un archivo denominado Test.htm.  
  
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
  
5.  Agregar un <xref:System.Windows.Forms.WebBrowser> control denominado `webBrowser1` al formulario principal de su proyecto.  
  
6.  Agregue el código siguiente al archivo de código del proyecto.  
  
    > [!IMPORTANT]
    >  Asegúrese de que el `webBrowser1_DocumentCompleted` controlador de eventos está configurado como un agente de escucha para el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos. En Visual Studio, haga doble clic en el <xref:System.Windows.Forms.WebBrowser> el control; en un editor de texto, configure el agente de escucha mediante programación.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  Ejecute el proyecto. Ejecute el cursor sobre la primera `DIV` para observar los efectos del código.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra el código completo para el `StyleGenerator` (clase), que analiza un valor de estilo existente, permite agregar, cambiar y quitar estilos y devuelve un nuevo valor de estilo con los cambios solicitados.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.HtmlElement>
