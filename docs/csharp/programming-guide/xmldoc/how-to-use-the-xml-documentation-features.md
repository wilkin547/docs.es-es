---
title: "C&#243;mo: Utilizar las caracter&#237;sticas de documentaci&#243;n XML (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "documentación XML [C#]"
  - "Lenguaje C#, características de documentación XML"
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# C&#243;mo: Utilizar las caracter&#237;sticas de documentaci&#243;n XML (Gu&#237;a de programaci&#243;n de C#)
El ejemplo siguiente proporciona una visión general básica de un tipo que se ha documentado.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **Este archivo .xml se generó con el ejemplo de código anterior.**  
**¿\<? xml versión = "1.0"?>**  
**\< doc.>**  
 **\< ensamblado>**  
 **\< nombre de>xmlsample \< / nombre>**  
 **\< / ensamblado>**  
 **\< miembros>**  
 **\< nombre de miembro = "T:SomeClass">**  
 **\< resumen>**  
 **Documentación resumida de nivel de clase va aquí. \< / resumen>**  
 **\< comentarios>**  
 **Comentarios más largos se pueden asociados con un tipo o miembro**   
 **con la etiqueta remarks \< / notas>**  
 **\< / miembro>**  
 **\< miembro name="F:SomeClass.m_Name">**  
 **\< resumen>**  
 **Almacén de la propiedad name \< / resumen>**  
 **\< / miembro>**  
 **\< nombre de miembro = "M:SomeClass. #ctor">**  
 **\< resumen>el constructor de clase. \< / resumen>**   
 **\< / miembro>**  
 **\< miembro name="M:SomeClass.SomeMethod(System.String)">**  
 **\< resumen>**  
 **Descripción de SomeMethod. \< / resumen>**  
 **\< nombre de parámetro = "s"> aquí la descripción del parámetro s \< / param>**  
 **\< seealso cref="T:System.String">**  
 **Puede utilizar el atributo cref con cualquier etiqueta para hacer referencia a un tipo o miembro**   
 **y el compilador comprobará que la referencia existe. \< / seealso>**  
 **\< / miembro>**  
 **\< miembro name="M:SomeClass.SomeOtherMethod">**  
 **\< resumen>**  
 **Algún otro método. \< / resumen>**  
 **\< devuelve>**  
 **Devolver resultados que se describen a través de la etiqueta devuelve. \< / devuelve>**  
 **\< seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **Observe el uso del atributo cref para hacer referencia a un método específico \< / seealso>**  
 **\< / miembro>**  
 **\< miembro name="M:SomeClass.Main(System.String[])">**  
 **\< resumen>**  
 **El punto de entrada para la aplicación.**  
 **\< / resumen>**  
 **\< nombre de parámetro = "args"> una lista de argumentos de línea de comandos \< / param>**  
 **\< / miembro>**  
 **\< miembro name="P:SomeClass.Name">**  
 **\< resumen>**  
 **Propiedad de nombre \< / resumen>**  
 **\< valor>**  
 **Una etiqueta de valor se utiliza para describir el valor de la propiedad \< / valor>**  
 **\< / miembro>**  
 **\< / miembros>**  
**\< / doc.>**   
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo, escriba la siguiente línea de comandos:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Esto creará el archivo XMLsample.xml, que se puede ver en el explorador o mediante el comando TYPE.  
  
## <a name="robust-programming"></a>Programación sólida  
 Documentación XML empieza con / / /. Cuando cree un nuevo proyecto, el asistente agrega algunas líneas de inicio / / / en automáticamente. El procesamiento de estos comentarios presenta algunas restricciones:  
  
-   La documentación debe ser correcto XML. Si el XML no está bien formado, se genera una advertencia y el archivo de documentación incluirá un comentario que dice que se detectó un error.  
  
-   Los desarrolladores pueden crear su propio conjunto de etiquetas. Hay un conjunto recomendado de etiquetas (consulte la sección información adicional). Algunas de las etiquetas recomendadas tienen significados especiales:  
  
    -   El \< param> etiqueta se utiliza para describir los parámetros. Si utiliza esta opción, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. Si la comprobación de errores, el compilador emite una advertencia.  
  
    -   El `cref` atributo se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprobará si existe ese elemento de código. Si la comprobación de errores, el compilador emite una advertencia. El compilador respeta cualquier `using` instrucciones cuando busca un tipo descrito en el `cref` atributo.  
  
    -   El \< resumen> etiqueta se utiliza IntelliSense en Visual Studio para mostrar información adicional sobre un tipo o miembro.  
  
        > [!NOTE]
        >  El archivo XML no proporciona información completa acerca de los tipos y miembros (por ejemplo, no contiene ninguna información de tipos). Para obtener información completa acerca de un tipo o miembro, el archivo de documentación debe utilizarse junto con la reflexión en el tipo o miembro.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [/doc (opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)