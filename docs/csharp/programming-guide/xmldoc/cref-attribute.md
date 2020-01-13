---
title: 'Atributo cref: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: 13bdfefaaa6f8daff0e7d9e30a6353af34654ba2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75697252"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="f5c42-102">Atributo cref (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f5c42-102">cref Attribute (C# Programming Guide)</span></span>
<span data-ttu-id="f5c42-103">El atributo `cref` en una etiqueta de documentación XML significa "referencia de código".</span><span class="sxs-lookup"><span data-stu-id="f5c42-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="f5c42-104">Especifica que el texto interno de la etiqueta es un elemento de código, como un tipo, un método o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f5c42-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="f5c42-105">En herramientas de documentación como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB), use los atributos `cref` para generar hipervínculos a la página donde se documenta el tipo o miembro de manera automática.</span><span class="sxs-lookup"><span data-stu-id="f5c42-105">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5c42-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5c42-106">Example</span></span>  
 <span data-ttu-id="f5c42-107">En el ejemplo siguiente se muestran los atributos `cref` que se usan en las etiquetas [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="f5c42-107">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]  
  
 <span data-ttu-id="f5c42-108">Cuando se compila, el programa genera el archivo XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5c42-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="f5c42-109">Observe que, por ejemplo, el compilador ha transformado el atributo `cref` del método `GetZero` en `"M:TestNamespace.TestClass.GetZero"`.</span><span class="sxs-lookup"><span data-stu-id="f5c42-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="f5c42-110">El prefijo "M:" significa "método", una convención reconocida por las herramientas de documentación tales como DocFX y Sandcastle.</span><span class="sxs-lookup"><span data-stu-id="f5c42-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="f5c42-111">Para obtener una lista completa de los prefijos, vea [Procesar el archivo XML](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="f5c42-111">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>CRefTest</name>  
    </assembly>  
    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains cref examples.  
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
    </members>    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains two cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example> This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
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
  
## <a name="see-also"></a><span data-ttu-id="f5c42-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5c42-112">See also</span></span>

- [<span data-ttu-id="f5c42-113">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="f5c42-113">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="f5c42-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="f5c42-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
