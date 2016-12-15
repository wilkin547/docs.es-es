---
title: "Delimitadores de etiquetas de documentaci&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/** */ (delimitadores de etiquetas de documentación en C#)"
  - "/// (delimitador para documentación en C#)"
  - "XML [C#], delimitadores"
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Delimitadores de etiquetas de documentaci&#243;n (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La utilización de comentarios de documentación XML requiere delimitadores, que indican al compilador el inicio y el final de un comentario de documentación.  Puede utilizar los siguientes tipos de delimitadores con las etiquetas de documentación XML:  
  
 `///`  
 Delimitador de una línea.  Ésta es la forma que se muestra en los ejemplos de documentación y que usan las plantillas de proyectos de Visual C\#.  Si hay un carácter de espacio en blanco que sigue el delimitador, ese carácter no está incluido en el XML generado.  
  
> [!NOTE]
>  El IDE de Visual Studio tiene una característica denominada Edición de comentarios automática, que inserta automáticamente las etiquetas \<summary\> y \<\/summary\> y sitúa el cursor entre ambas después de que haya escrito el delimitador `///` en el Editor de código.  El acceso a esta característica se encuentra en [Opciones, editor de texto, C\#, formato](/visual-studio/ide/reference/options-text-editor-csharp-formatting) en sus páginas de propiedad del proyecto.  
  
 `/** */`  
 Delimitadores de múltiples líneas.  
  
 Existen algunas reglas de formato a seguir cuando se usan los delimitadores `/** */`.  
  
-   En el resto de la línea que contiene el delimitador `/**`  está en blanco, la línea no se procesa para comentarios.  Si el primer carácter después del delimitador `/**`  es un espacio en blanco, éste se omite y se procesa el resto de la línea.  En caso contrario, todo el texto de la línea que se encuentra después del delimitador `/**` se procesa como parte del comentario.  
  
-   En la línea que contiene el delimitador `*/` , si sólo hay espacio en blanco hasta el delimitador `*/`, se omite la línea.  En caso contrario, el texto que hay en la línea hasta el delimitador `*/` se procesa como parte del comentario, sujeto a las reglas del patrón de coincidencia que se describen en el apartado siguiente:  
  
-   Para las líneas después de la que comienza con el delimitador `/**`, el compilador busca al principio un modelo común de cada línea.  El modelo puede estar compuesto de espacios en blanco opcionales y un asterisco \(`*`, seguidos por más espacios en blanco opcionales.  Si el compilador encuentra un modelo común al principio de cada línea que no comienza con el delimitador `/**` o el delimitador `*/`, omite ese modelo para cada línea.  
  
 En el ejemplo siguiente se muestran estas reglas.  
  
-   La única parte del siguiente comentario que se procesará es la línea que comienza con `<summary>`.  Los tres formatos de etiquetas producen los mismos comentarios.  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
  
    ```  
  
-   El compilador identifica un modelo común de " \* " al principio de la segunda y tercera líneas.  El modelo no está incluido en el resultado.  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   El compilador no encuentra ningún modelo común en el siguiente comentario porque el segundo carácter en la tercera línea no es un asterisco.  Por lo tanto, todo el texto que hay en la segunda y tercera líneas se procesará como parte del comentario.  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   El compilador no encuentra ningún patrón en el siguiente comentario por dos razones.  Primero, el número de espacios delante del asterisco no es coherente.  En segundo lugar, la quinta línea comienza con una etiqueta, que no coincide con los espacios.  Por consiguiente, todo el texto desde la segunda hasta la quinta línea se procesa como parte del comentario.  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)