---
title: 'Delimitadores de etiquetas de documentación: guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: dd4ddb3b324bd6d235efb541c90875dbe9ed4c2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789831"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="ff066-102">Delimitadores de etiquetas de documentación (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ff066-102">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="ff066-103">El uso de comentarios de documentación XML requiere delimitadores, que le indican al compilador dónde empieza y dónde acaba un comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="ff066-103">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="ff066-104">Puede usar los siguientes tipos de delimitadores con las etiquetas de documentación XML:</span><span class="sxs-lookup"><span data-stu-id="ff066-104">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="ff066-105">Delimitador de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="ff066-105">Single-line delimiter.</span></span> <span data-ttu-id="ff066-106">Este es el formulario que se muestra en los ejemplos de documentación y que usan las plantillas de proyecto de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ff066-106">This is the form that is shown in documentation examples and used by the Visual C# project templates.</span></span> <span data-ttu-id="ff066-107">Si hay un carácter de espacio en blanco después del delimitador, ese carácter no se incluye en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="ff066-107">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ff066-108">El IDE de Visual Studio tiene una característica denominada Smart Comment Editing (Edición de comentarios inteligente) que inserta automáticamente las etiquetas \<summary> y \</summary> y mueve el cursor dentro de estas etiquetas después de escribir el delimitador `///` en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="ff066-108">The Visual Studio IDE has a feature called Smart Comment Editing that automatically inserts the \<summary> and \</summary> tags and moves your cursor within these tags after you type the `///` delimiter in the Code Editor.</span></span> <span data-ttu-id="ff066-109">Puede activar o desactivar esta característica en el [cuadro de diálogo Opciones](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span><span class="sxs-lookup"><span data-stu-id="ff066-109">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="ff066-110">Delimitadores de múltiples líneas.</span><span class="sxs-lookup"><span data-stu-id="ff066-110">Multiline delimiters.</span></span>

  <span data-ttu-id="ff066-111">Debe seguir ciertas reglas de formato cuando use los delimitadores `/** */`:</span><span class="sxs-lookup"><span data-stu-id="ff066-111">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="ff066-112">En la línea que contiene el delimitador `/**`, si el resto de la línea es espacio en blanco, la línea no se procesa en busca de comentarios.</span><span class="sxs-lookup"><span data-stu-id="ff066-112">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="ff066-113">Si el primer carácter después del delimitador `/**` es un espacio en blanco, dicho carácter de espacio en blanco se omite y se procesa el resto de la línea.</span><span class="sxs-lookup"><span data-stu-id="ff066-113">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="ff066-114">En caso contrario, todo el texto de la línea situado después del delimitador `/**` se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="ff066-114">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="ff066-115">En la línea que contiene el delimitador `*/`, si solo hay espacio en blanco hasta el delimitador `*/`, esa línea se omite.</span><span class="sxs-lookup"><span data-stu-id="ff066-115">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="ff066-116">En caso contrario, el texto de la línea hasta el delimitador `*/` se procesa como parte del comentario y está sujeto a las reglas de coincidencia de patrones que se describen en el punto siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff066-116">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment, subject to the pattern-matching rules described in the following bullet.</span></span>
  
  - <span data-ttu-id="ff066-117">Para las líneas que aparecen después de la que comienza con el delimitador `/**`, el compilador busca un patrón común al principio de cada línea.</span><span class="sxs-lookup"><span data-stu-id="ff066-117">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="ff066-118">El patrón puede consistir en un espacio en blanco opcional y un asterisco (`*`), seguido de otro espacio en blanco opcional.</span><span class="sxs-lookup"><span data-stu-id="ff066-118">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="ff066-119">Si el compilador encuentra un patrón común al principio de cada línea que no empieza por el delimitador `/**` o el delimitador `*/`, omite ese patrón para cada línea.</span><span class="sxs-lookup"><span data-stu-id="ff066-119">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="ff066-120">En los siguientes ejemplos se muestran estas reglas.</span><span class="sxs-lookup"><span data-stu-id="ff066-120">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="ff066-121">La única parte del comentario siguiente que se procesará es la línea que comienza con `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="ff066-121">The only part of the following comment that will be processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="ff066-122">Los tres formatos de etiquetas producen los mismos comentarios.</span><span class="sxs-lookup"><span data-stu-id="ff066-122">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="ff066-123">El compilador identifica un patrón común de " \* " al principio de la segunda y la tercera línea.</span><span class="sxs-lookup"><span data-stu-id="ff066-123">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="ff066-124">El patrón no se incluye en la salida.</span><span class="sxs-lookup"><span data-stu-id="ff066-124">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="ff066-125">El compilador no encuentra ningún patrón común en el comentario siguiente porque el segundo carácter de la tercera línea no es un asterisco.</span><span class="sxs-lookup"><span data-stu-id="ff066-125">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="ff066-126">Por lo tanto, todo el texto de la segunda y la tercera línea se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="ff066-126">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="ff066-127">El compilador no encuentra ningún patrón en el comentario siguiente por dos razones.</span><span class="sxs-lookup"><span data-stu-id="ff066-127">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="ff066-128">En primer lugar, el número de espacios antes del asterisco no es coherente.</span><span class="sxs-lookup"><span data-stu-id="ff066-128">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="ff066-129">En segundo lugar, la quinta línea comienza con una tabulación, por lo tanto los espacios no coinciden.</span><span class="sxs-lookup"><span data-stu-id="ff066-129">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="ff066-130">Como resultado, todo el texto de las líneas de la dos a la cinco se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="ff066-130">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

    <!-- markdownlint-disable MD010 -->
    ```csharp
    /**
      * <summary>
      * text
     *  text2
        *  </summary>
    */
    ```
    <!-- markdownlint-enable MD010 -->

## <a name="see-also"></a><span data-ttu-id="ff066-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff066-131">See also</span></span>

- [<span data-ttu-id="ff066-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ff066-132">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ff066-133">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="ff066-133">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="ff066-134">-doc (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ff066-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
