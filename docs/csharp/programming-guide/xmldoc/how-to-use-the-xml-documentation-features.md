---
title: 'Procedimiento para usar las características de documentación XML: Guía de programación de C#'
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 5de94b1f1ab44f954b5bab9f8b5212c33325c19d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696719"
---
# <a name="how-to-use-the-xml-documentation-features"></a>Procedimiento para usar las características de la documentación XML

En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

El ejemplo genera un archivo .xml con el siguiente contenido:

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member 
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a>Compilación del código

Para compilar el ejemplo, escriba la siguiente línea de comandos:

`csc XMLsample.cs /doc:XMLsample.xml`

Este comando crea el archivo XML *XMLsample.xml*, que se puede ver en el explorador o mediante el comando TYPE.

## <a name="robust-programming"></a>Programación sólida

La documentación XML empieza con ///. Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///. El procesamiento de estos comentarios tiene algunas restricciones:

- La documentación debe ser XML con formato correcto. Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.

- Los desarrolladores pueden crear su propio conjunto de etiquetas, Hay un conjunto de etiquetas recomendado (consulte [Etiquetas recomendadas para los comentarios de documentación](recommended-tags-for-documentation-comments.md)). Algunas de las etiquetas recomendadas tienen significados especiales:

  - La etiqueta \<param> se usa para describir parámetros. Si se usa, el compilador comprueba que el parámetro existe y que todos los parámetros se describen en la documentación. Si se produce un error en la comprobación, el compilador emite una advertencia.

  - El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código. El compilador comprueba si existe este elemento de código. Si se produce un error en la comprobación, el compilador emite una advertencia. El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.

  - IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.

    > [!NOTE]
    > El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos). Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [-doc (Opciones del compilador de C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Comentarios de documentación XML](./index.md)
- [Procesador de documentación de DocFX](https://dotnet.github.io/docfx/)
- [Procesador de documentación de Sandcastle](https://github.com/EWSoftware/SHFB)
