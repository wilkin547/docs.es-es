---
title: "Delimitadores de etiquetas de documentación (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ba3b38a8bce9f5b49ef863acfae04bc2a39c052a
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a>Delimitadores de etiquetas de documentación (Guía de programación de C#)
El uso de comentarios de documentación XML requiere delimitadores, que le indican al compilador dónde empieza y dónde acaba un comentario de documentación. Puede usar los siguientes tipos de delimitadores con las etiquetas de documentación XML:  
  
 `///`  
 Delimitador de una sola línea. Este es el formulario que se muestra en los ejemplos de documentación y que usan las plantillas de proyecto de Visual C#. Si hay un carácter de espacio en blanco después del delimitador, ese carácter no se incluye en la salida XML.  
  
> [!NOTE]
>  El IDE de Visual Studio tiene una característica denominada Smart Comment Editing (Edición de comentarios inteligente) que inserta automáticamente las etiquetas \<summary> y \</summary> y mueve el cursor dentro de estas etiquetas después de escribir el delimitador `///` en el Editor de código. Para obtener acceso a esta función, vaya a [Opciones, Editor de texto, C#, Formato](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-csharp-formatting) en las páginas de propiedades del proyecto.  
  
 `/** */`  
 Delimitadores de múltiples líneas.  
  
 Debe seguir ciertas reglas de formato cuando use los delimitadores `/** */`.  
  
-   En la línea que contiene el delimitador `/**`, si el resto de la línea es espacio en blanco, la línea no se procesa en busca de comentarios. Si el primer carácter después del delimitador `/**` es un espacio en blanco, dicho carácter de espacio en blanco se omite y se procesa el resto de la línea. En caso contrario, todo el texto de la línea situado después del delimitador `/**` se procesa como parte del comentario.  
  
-   En la línea que contiene el delimitador `*/`, si solo hay espacio en blanco hasta el delimitador `*/`, esa línea se omite. En caso contrario, el texto de la línea hasta el delimitador `*/` se procesa como parte del comentario y está sujeto a las reglas de coincidencia de patrones que se describen en el punto siguiente.  
  
-   Para las líneas que aparecen después de la que comienza con el delimitador `/**`, el compilador busca un patrón común al principio de cada línea. El patrón puede consistir en un espacio en blanco opcional y un asterisco (`*`), seguido de otro espacio en blanco opcional. Si el compilador encuentra un patrón común al principio de cada línea que no empieza por el delimitador `/**` o el delimitador `*/`, omite ese patrón para cada línea.  
  
 En los siguientes ejemplos se muestran estas reglas.  
  
-   La única parte del comentario siguiente que se procesará es la línea que comienza con `<summary>`. Los tres formatos de etiquetas producen los mismos comentarios.  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
-   El compilador identifica un patrón común de " * " al principio de la segunda y la tercera línea. El patrón no se incluye en la salida.  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   El compilador no encuentra ningún patrón común en el comentario siguiente porque el segundo carácter de la tercera línea no es un asterisco. Por lo tanto, todo el texto de la segunda y la tercera línea se procesa como parte del comentario.  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   El compilador no encuentra ningún patrón en el comentario siguiente por dos razones. En primer lugar, el número de espacios antes del asterisco no es coherente. En segundo lugar, la quinta línea comienza con una tabulación, por lo tanto los espacios no coinciden. Como resultado, todo el texto de las líneas de la dos a la cinco se procesa como parte del comentario.  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)   
 [/doc (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

