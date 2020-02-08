---
title: 'Atributo cref: guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: 2a9b9966a28b62c41ac6091268ae172bae3a40d7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793443"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="95914-102">Atributo cref (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="95914-102">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="95914-103">El atributo `cref` en una etiqueta de documentación XML significa "referencia de código".</span><span class="sxs-lookup"><span data-stu-id="95914-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="95914-104">Especifica que el texto interno de la etiqueta es un elemento de código, como un tipo, un método o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="95914-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="95914-105">En herramientas de documentación como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB), use los atributos `cref` para generar hipervínculos a la página donde se documenta el tipo o miembro de manera automática.</span><span class="sxs-lookup"><span data-stu-id="95914-105">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="95914-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95914-106">Example</span></span>

<span data-ttu-id="95914-107">En el ejemplo siguiente se muestran los atributos `cref` que se usan en las etiquetas [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="95914-107">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="95914-108">Cuando se compila, el programa genera el archivo XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="95914-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="95914-109">Observe que, por ejemplo, el compilador ha transformado el atributo `cref` del método `GetZero` en `"M:TestNamespace.TestClass.GetZero"`.</span><span class="sxs-lookup"><span data-stu-id="95914-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="95914-110">El prefijo "M:" significa "método", una convención reconocida por las herramientas de documentación tales como DocFX y Sandcastle.</span><span class="sxs-lookup"><span data-stu-id="95914-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="95914-111">Para obtener una lista completa de los prefijos, vea [Procesar el archivo XML](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="95914-111">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="95914-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="95914-112">See also</span></span>

- [<span data-ttu-id="95914-113">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="95914-113">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="95914-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="95914-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
