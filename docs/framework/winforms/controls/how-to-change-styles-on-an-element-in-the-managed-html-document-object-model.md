---
title: Procedimiento para cambiar los estilos de un elemento en Document Object Model HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 804041991199dd2722e3a0f38800bafd8933bbab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333670"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Procedimiento para cambiar los estilos de un elemento en Document Object Model HTML administrado

Puede usar los estilos en HTML para controlar la apariencia de un documento y sus elementos. <xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> admite <xref:System.Windows.Forms.HtmlElement.Style%2A> propiedades que toman cadenas de estilo del formato siguiente:

`name1:value1;...;nameN:valueN;`

Este es un `DIV` con una cadena de estilo que establece la fuente en Arial y todo el texto en negrita:

`<DIV style="font-face:arial;font-weight:bold;">`

`Hello, world!`

`</DIV>`

El problema de manipular estilos utilizando el <xref:System.Windows.Forms.HtmlElement.Style%2A> propiedad es que puede resultar complicado para agregar y quitar la configuración de estilo individuales de la cadena. Por ejemplo, convertiría en un procedimiento complejo para representar el texto en cursiva anterior siempre que el usuario coloca el cursor sobre la `DIV`y tomar cursiva desactivada cuando el cursor abandona el `DIV`. Tiempo podría ser un problema si necesita manipular un gran número de estilos de esta manera.

El procedimiento siguiente contiene código que puede usar para manipular fácilmente los estilos de elementos y documentos HTML. El procedimiento requiere que sepa cómo realizar tareas básicas en los formularios de Windows, como crear un nuevo proyecto y agregar un control a un formulario.

### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Para procesar los cambios de estilo en una aplicación Windows Forms

1. Cree un nuevo proyecto de Windows Forms.

2. Cree un nuevo archivo de clase termina en extensión adecuada para su lenguaje de programación.

3. Copia el `StyleGenerator` código en la sección de ejemplo de este tema de la clase en el archivo de clase y guarde el código.

4. Guarde el siguiente código HTML en un archivo denominado Test.htm.

    ```html
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

5. Agregar un <xref:System.Windows.Forms.WebBrowser> control denominado `webBrowser1` al formulario principal de su proyecto.

6. Agregue el código siguiente al archivo de código del proyecto.

    > [!IMPORTANT]
    >  Asegúrese de que el `webBrowser1_DocumentCompleted` controlador de eventos está configurado como un agente de escucha para el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos. En Visual Studio, haga doble clic en el <xref:System.Windows.Forms.WebBrowser> control; en un editor de texto, configure el agente de escucha mediante programación.  
  
     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7. Ejecute el proyecto. Ejecute el cursor sobre la primera `DIV` para observar los efectos del código.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra el código completo para el `StyleGenerator` admite clase, que analiza un valor de estilo existente, agregar, cambiar y quitar los estilos y devuelve un nuevo valor de estilo con los cambios solicitados.  
  
 [!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.HtmlElement>
