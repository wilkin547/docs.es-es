---
title: 'Cómo: Utilizar las características de documentación XML (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: d7f1f51040033cf25f7f1aefb04d249e6e028ca3
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472781"
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Cómo: Utilizar las características de documentación XML (Guía de programación de C#)
En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  

El ejemplo genera un archivo .xml con el siguiente contenido:

```xml  
<?xml version="1.0"?>  
<doc>  
 <assembly>  
 <name>xmlsample</name>  
 </assembly>  
 <members>  
 <member name="T:SomeClass">  
 <summary>  
 Class level summary documentation goes here.</summary>  
 <remarks>  
 Longer comments can be associated with a type or member  
 through the remarks tag</remarks>  
 </member>  
 <member name="F:SomeClass.m_Name">  
 <summary>  
 Store for the name property</summary>  
 </member>  
 <member name="M:SomeClass.#ctor">  
 <summary>The class constructor.</summary>  
 </member>  
 <member name="M:SomeClass.SomeMethod(System.String)">  
 <summary>  
 Description for SomeMethod.</summary>  
 <param name="s"> Parameter description for s goes here</param>  
 <seealso cref="T:System.String">  
 You can use the cref attribute on any tag to reference a type or member  
 and the compiler will check that the reference exists. </seealso>  
 </member>  
 <member name="M:SomeClass.SomeOtherMethod">  
 <summary>  
 Some other method. </summary>  
 <returns>  
 Return results are described through the returns tag.</returns>  
 <seealso cref="M:SomeClass.SomeMethod(System.String)">  
 Notice the use of the cref attribute to reference a specific method </seealso>  
 </member>  
 <member name="M:SomeClass.Main(System.String[])">  
 <summary>  
 The entry point for the application.  
 </summary>  
 <param name="args"> A list of command line arguments</param>  
 </member>  
 <member name="P:SomeClass.Name">  
 <summary>  
 Name property </summary>  
 <value>A value tag is used to describe the property value</value>  
 </member>  
 </members>  
</doc>   
```

## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo, escriba la siguiente línea de comandos:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Esto creará el archivo XML XMLsample.xml, que se puede ver en el explorador o mediante el comando TYPE.  
  
## <a name="robust-programming"></a>Programación sólida  
 La documentación XML empieza con ///. Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///. El procesamiento de estos comentarios tiene algunas restricciones:  
  
-   La documentación debe ser XML con formato correcto. Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.  
  
-   Los desarrolladores pueden crear su propio conjunto de etiquetas, Hay un conjunto de etiquetas recomendado (consulte [Etiquetas recomendadas para los comentarios de documentación](recommended-tags-for-documentation-comments.md)). Algunas de las etiquetas recomendadas tienen significados especiales:  
  
    -   La etiqueta \<param> se usa para describir parámetros. Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación. Si se produce un error en la comprobación, el compilador emite una advertencia.  
  
    -   El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprobará si existe ese elemento de código. Si se produce un error en la comprobación, el compilador emite una advertencia. El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.  
  
    -   IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.  
  
        > [!NOTE]
        >  El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos). Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [/doc (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
