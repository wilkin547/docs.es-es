---
title: 'Delimitadores de etiquetas de documentación: guía de programación de C#'
description: Aprenda sobre los delimitadores para las etiquetas de documentación. Los delimitadores indican al compilador dónde comienza y termina un comentario de documentación.
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 3191e32b0ff2dbde004abaab0b699cd61fcbb150
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381988"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="64b53-104">Delimitadores de etiquetas de documentación (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="64b53-104">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="64b53-105">El uso de comentarios de documentación XML requiere delimitadores, que le indican al compilador dónde empieza y dónde acaba un comentario de documentación.</span><span class="sxs-lookup"><span data-stu-id="64b53-105">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="64b53-106">Puede usar los siguientes tipos de delimitadores con las etiquetas de documentación XML:</span><span class="sxs-lookup"><span data-stu-id="64b53-106">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="64b53-107">Delimitador de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="64b53-107">Single-line delimiter.</span></span> <span data-ttu-id="64b53-108">Este es el formato que se muestra en los ejemplos de documentación y que usan las plantillas de proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="64b53-108">This is the form that is shown in documentation examples and used by the C# project templates.</span></span> <span data-ttu-id="64b53-109">Si hay un carácter de espacio en blanco después del delimitador, ese carácter no se incluye en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="64b53-109">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="64b53-110">El entorno de desarrollo integrado (IDE) de Visual Studio inserta automáticamente las etiquetas `<summary>` y `</summary>` y mueve el cursor dentro de estas etiquetas después de escribir el delimitador `///` en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="64b53-110">The Visual Studio integrated development environment (IDE) automatically inserts the `<summary>` and `</summary>` tags and moves your cursor within these tags after you type the `///` delimiter in the code editor.</span></span> <span data-ttu-id="64b53-111">Puede activar o desactivar esta característica en el [cuadro de diálogo Opciones](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span><span class="sxs-lookup"><span data-stu-id="64b53-111">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="64b53-112">Delimitadores de múltiples líneas.</span><span class="sxs-lookup"><span data-stu-id="64b53-112">Multiline delimiters.</span></span>

  <span data-ttu-id="64b53-113">Debe seguir ciertas reglas de formato cuando use los delimitadores `/** */`:</span><span class="sxs-lookup"><span data-stu-id="64b53-113">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="64b53-114">En la línea que contiene el delimitador `/**`, si el resto de la línea es espacio en blanco, la línea no se procesa en busca de comentarios.</span><span class="sxs-lookup"><span data-stu-id="64b53-114">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="64b53-115">Si el primer carácter después del delimitador `/**` es un espacio en blanco, dicho carácter de espacio en blanco se omite y se procesa el resto de la línea.</span><span class="sxs-lookup"><span data-stu-id="64b53-115">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="64b53-116">En caso contrario, todo el texto de la línea situado después del delimitador `/**` se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="64b53-116">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="64b53-117">En la línea que contiene el delimitador `*/`, si solo hay espacio en blanco hasta el delimitador `*/`, esa línea se omite.</span><span class="sxs-lookup"><span data-stu-id="64b53-117">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="64b53-118">En caso contrario, el texto de la línea situado antes del delimitador `*/` se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="64b53-118">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment.</span></span>
  
  - <span data-ttu-id="64b53-119">Para las líneas que aparecen después de la que comienza con el delimitador `/**`, el compilador busca un patrón común al principio de cada línea.</span><span class="sxs-lookup"><span data-stu-id="64b53-119">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="64b53-120">El patrón puede consistir en un espacio en blanco opcional y un asterisco (`*`), seguido de otro espacio en blanco opcional.</span><span class="sxs-lookup"><span data-stu-id="64b53-120">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="64b53-121">Si el compilador encuentra un patrón común al principio de cada línea que no empieza por el delimitador `/**` o el delimitador `*/`, omite ese patrón para cada línea.</span><span class="sxs-lookup"><span data-stu-id="64b53-121">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="64b53-122">En los siguientes ejemplos se muestran estas reglas.</span><span class="sxs-lookup"><span data-stu-id="64b53-122">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="64b53-123">La única parte del comentario siguiente que se procesará es la línea que comienza con `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="64b53-123">The only part of the following comment that's processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="64b53-124">Los tres formatos de etiquetas producen los mismos comentarios.</span><span class="sxs-lookup"><span data-stu-id="64b53-124">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="64b53-125">El compilador identifica un patrón común de " \* " al principio de la segunda y la tercera línea.</span><span class="sxs-lookup"><span data-stu-id="64b53-125">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="64b53-126">El patrón no se incluye en la salida.</span><span class="sxs-lookup"><span data-stu-id="64b53-126">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="64b53-127">El compilador no encuentra ningún patrón común en el comentario siguiente porque el segundo carácter de la tercera línea no es un asterisco.</span><span class="sxs-lookup"><span data-stu-id="64b53-127">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="64b53-128">Por lo tanto, todo el texto de la segunda y la tercera línea se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="64b53-128">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="64b53-129">El compilador no encuentra ningún patrón en el comentario siguiente por dos razones.</span><span class="sxs-lookup"><span data-stu-id="64b53-129">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="64b53-130">En primer lugar, el número de espacios antes del asterisco no es coherente.</span><span class="sxs-lookup"><span data-stu-id="64b53-130">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="64b53-131">En segundo lugar, la quinta línea comienza con una tabulación, por lo tanto los espacios no coinciden.</span><span class="sxs-lookup"><span data-stu-id="64b53-131">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="64b53-132">Como resultado, todo el texto de las líneas de la dos a la cinco se procesa como parte del comentario.</span><span class="sxs-lookup"><span data-stu-id="64b53-132">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="64b53-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="64b53-133">See also</span></span>

- [<span data-ttu-id="64b53-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="64b53-134">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="64b53-135">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="64b53-135">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="64b53-136">-doc (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="64b53-136">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
