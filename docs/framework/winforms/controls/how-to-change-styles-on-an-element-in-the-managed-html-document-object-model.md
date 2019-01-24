---
title: Procedimiento Cambiar los estilos de un elemento en el modelo de objetos de documento HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 0db67936e368c1cb6d942b348ebacd87b6127e19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579386"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="44a7c-102">Procedimiento Cambiar los estilos de un elemento en el modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="44a7c-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="44a7c-103">Puede usar los estilos en HTML para controlar la apariencia de un documento y sus elementos.</span><span class="sxs-lookup"><span data-stu-id="44a7c-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="44a7c-104"><xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> admite <xref:System.Windows.Forms.HtmlElement.Style%2A> propiedades que toman cadenas de estilo del formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="44a7c-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>  
  
 `name1:value1;...;nameN:valueN;`  
  
 <span data-ttu-id="44a7c-105">Este es un `DIV` con una cadena de estilo que establece la fuente en Arial y todo el texto en negrita:</span><span class="sxs-lookup"><span data-stu-id="44a7c-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 <span data-ttu-id="44a7c-106">El problema de manipular estilos utilizando el <xref:System.Windows.Forms.HtmlElement.Style%2A> propiedad es que puede resultar complicado para agregar y quitar la configuración de estilo individuales de la cadena.</span><span class="sxs-lookup"><span data-stu-id="44a7c-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="44a7c-107">Por ejemplo, convertiría en un procedimiento complejo para representar el texto en cursiva anterior siempre que el usuario coloca el cursor sobre la `DIV`y tomar cursiva desactivada cuando el cursor abandona el `DIV`.</span><span class="sxs-lookup"><span data-stu-id="44a7c-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="44a7c-108">Tiempo podría ser un problema si necesita manipular un gran número de estilos de esta manera.</span><span class="sxs-lookup"><span data-stu-id="44a7c-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>  
  
 <span data-ttu-id="44a7c-109">El procedimiento siguiente contiene código que puede usar para manipular fácilmente los estilos de elementos y documentos HTML.</span><span class="sxs-lookup"><span data-stu-id="44a7c-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="44a7c-110">El procedimiento requiere que sepa cómo realizar tareas básicas en los formularios de Windows, como crear un nuevo proyecto y agregar un control a un formulario.</span><span class="sxs-lookup"><span data-stu-id="44a7c-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="44a7c-111">Para procesar los cambios de estilo en una aplicación Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44a7c-111">To process style changes in a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="44a7c-112">Cree un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="44a7c-112">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="44a7c-113">Cree un nuevo archivo de clase termina en extensión adecuada para su lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="44a7c-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>  
  
3.  <span data-ttu-id="44a7c-114">Copia el `StyleGenerator` código en la sección de ejemplo de este tema de la clase en el archivo de clase y guarde el código.</span><span class="sxs-lookup"><span data-stu-id="44a7c-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>  
  
4.  <span data-ttu-id="44a7c-115">Guarde el siguiente código HTML en un archivo denominado Test.htm.</span><span class="sxs-lookup"><span data-stu-id="44a7c-115">Save the following HTML to a file named Test.htm.</span></span>  
  
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
  
5.  <span data-ttu-id="44a7c-116">Agregar un <xref:System.Windows.Forms.WebBrowser> control denominado `webBrowser1` al formulario principal de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="44a7c-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>  
  
6.  <span data-ttu-id="44a7c-117">Agregue el código siguiente al archivo de código del proyecto.</span><span class="sxs-lookup"><span data-stu-id="44a7c-117">Add the following code to your project's code file.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="44a7c-118">Asegúrese de que el `webBrowser1_DocumentCompleted` controlador de eventos está configurado como un agente de escucha para el <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> eventos.</span><span class="sxs-lookup"><span data-stu-id="44a7c-118">Ensure that the `webBrowser1_DocumentCompleted` event hander is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="44a7c-119">En Visual Studio, haga doble clic en el <xref:System.Windows.Forms.WebBrowser> control; en un editor de texto, configure el agente de escucha mediante programación.</span><span class="sxs-lookup"><span data-stu-id="44a7c-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  <span data-ttu-id="44a7c-120">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="44a7c-120">Run the project.</span></span> <span data-ttu-id="44a7c-121">Ejecute el cursor sobre la primera `DIV` para observar los efectos del código.</span><span class="sxs-lookup"><span data-stu-id="44a7c-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44a7c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44a7c-122">Example</span></span>  
 <span data-ttu-id="44a7c-123">El ejemplo de código siguiente muestra el código completo para el `StyleGenerator` admite clase, que analiza un valor de estilo existente, agregar, cambiar y quitar los estilos y devuelve un nuevo valor de estilo con los cambios solicitados.</span><span class="sxs-lookup"><span data-stu-id="44a7c-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="44a7c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="44a7c-124">See also</span></span>
- <xref:System.Windows.Forms.HtmlElement>
