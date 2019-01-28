---
title: '&lt;summary&gt;: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5447b9ea129c26fdbb9effe1a3aeac6d7290764a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740039"
---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="675b2-102">&lt;summary&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="675b2-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="675b2-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="675b2-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="675b2-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="675b2-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="675b2-105">Resumen del objeto.</span><span class="sxs-lookup"><span data-stu-id="675b2-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="675b2-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="675b2-106">Remarks</span></span>  
 <span data-ttu-id="675b2-107">La etiqueta \<summary> debe usarse para describir un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="675b2-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="675b2-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) para agregar información adicional a una descripción de tipo.</span><span class="sxs-lookup"><span data-stu-id="675b2-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="675b2-109">Use el [atributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) para permitir que herramientas de documentación como [Sandcastle](https://github.com/EWSoftware/SHFB) creen hipervínculos internos a las páginas de documentación de los elementos de código.</span><span class="sxs-lookup"><span data-stu-id="675b2-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="675b2-110">El texto de la etiqueta \<summary> es la única fuente de información sobre el tipo en IntelliSense y también se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="675b2-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="675b2-111">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="675b2-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="675b2-112">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="675b2-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="675b2-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="675b2-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 <span data-ttu-id="675b2-114">En el ejemplo anterior se genera el siguiente archivo XML.</span><span class="sxs-lookup"><span data-stu-id="675b2-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="675b2-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="675b2-115">Example</span></span>  
 <span data-ttu-id="675b2-116">En el ejemplo siguiente se muestra cómo hacer una referencia `cref` a un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="675b2-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 <span data-ttu-id="675b2-117">En el ejemplo anterior se genera el siguiente archivo XML.</span><span class="sxs-lookup"><span data-stu-id="675b2-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="675b2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="675b2-118">See also</span></span>

- [<span data-ttu-id="675b2-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="675b2-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="675b2-120">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="675b2-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
