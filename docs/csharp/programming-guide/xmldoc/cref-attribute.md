---
title: 'Atributo cref: guía de programación de C#'
description: Aprenda sobre el atributo cref. El atributo cref significa "referencia de código" y especifica que el texto interno de la etiqueta es un elemento de código.
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: 31fa1a3f182d7b72a1dfbe1ce47386f87fbbff75
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382001"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="06e2c-104">Atributo cref (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="06e2c-104">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="06e2c-105">El atributo `cref` en una etiqueta de documentación XML significa "referencia de código".</span><span class="sxs-lookup"><span data-stu-id="06e2c-105">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="06e2c-106">Especifica que el texto interno de la etiqueta es un elemento de código, como un tipo, un método o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="06e2c-106">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="06e2c-107">En herramientas de documentación como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB), use los atributos `cref` para generar hipervínculos a la página donde se documenta el tipo o miembro de manera automática.</span><span class="sxs-lookup"><span data-stu-id="06e2c-107">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="06e2c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06e2c-108">Example</span></span>

<span data-ttu-id="06e2c-109">En el ejemplo siguiente se muestran los atributos `cref` que se usan en las etiquetas [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="06e2c-109">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="06e2c-110">Cuando se compila, el programa genera el archivo XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="06e2c-110">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="06e2c-111">Observe que, por ejemplo, el compilador ha transformado el atributo `cref` del método `GetZero` en `"M:TestNamespace.TestClass.GetZero"`.</span><span class="sxs-lookup"><span data-stu-id="06e2c-111">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="06e2c-112">El prefijo "M:" significa "método", una convención reconocida por las herramientas de documentación tales como DocFX y Sandcastle.</span><span class="sxs-lookup"><span data-stu-id="06e2c-112">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="06e2c-113">Para obtener una lista completa de los prefijos, vea [Procesar el archivo XML](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="06e2c-113">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="06e2c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06e2c-114">See also</span></span>

- [<span data-ttu-id="06e2c-115">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="06e2c-115">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="06e2c-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="06e2c-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
