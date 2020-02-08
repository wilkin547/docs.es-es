---
title: 'Etiquetas recomendadas para comentarios de documentación: guía de programación de C#'
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789722"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="46109-102">Etiquetas recomendadas para comentarios de documentación (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="46109-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="46109-103">El compilador de C# procesa los comentarios de documentación de su código y les aplica formato como XML en un archivo cuyo nombre especifica en la opción de línea de comandos **/doc**.</span><span class="sxs-lookup"><span data-stu-id="46109-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="46109-104">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="46109-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="46109-105">Las etiquetas se procesan en construcciones de código como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="46109-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="46109-106">Los comentarios de documentación no pueden aplicarse en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="46109-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="46109-107">El compilador procesará cualquier etiqueta que sea un XML válido.</span><span class="sxs-lookup"><span data-stu-id="46109-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="46109-108">Las siguientes etiquetas proporcionan funciones de uso general en la documentación de usuario.</span><span class="sxs-lookup"><span data-stu-id="46109-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="46109-109">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="46109-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="46109-110">\<c></span><span class="sxs-lookup"><span data-stu-id="46109-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="46109-111">\<para></span><span class="sxs-lookup"><span data-stu-id="46109-111">\<para></span></span>](./para.md)|<span data-ttu-id="46109-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="46109-113">\<value></span><span class="sxs-lookup"><span data-stu-id="46109-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="46109-114">\<code></span><span class="sxs-lookup"><span data-stu-id="46109-114">\<code></span></span>](./code.md)|<span data-ttu-id="46109-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="46109-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="46109-117">\<example></span><span class="sxs-lookup"><span data-stu-id="46109-117">\<example></span></span>](./example.md)|[<span data-ttu-id="46109-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="46109-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="46109-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="46109-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="46109-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="46109-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="46109-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="46109-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="46109-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="46109-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="46109-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="46109-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="46109-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="46109-126">\<list></span><span class="sxs-lookup"><span data-stu-id="46109-126">\<list></span></span>](./list.md)|[<span data-ttu-id="46109-127">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="46109-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="46109-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="46109-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="46109-129">(\* denota que el compilador comprueba la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="46109-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="46109-130">Si quiere que aparezcan corchetes angulares en el texto de un comentario de documentación, utilice la codificación HTML de `<` y `>`, que es `&lt;` y `&gt;` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="46109-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="46109-131">Esta codificación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="46109-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="46109-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="46109-132">See also</span></span>

- [<span data-ttu-id="46109-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="46109-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="46109-134">-doc (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="46109-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="46109-135">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="46109-135">XML documentation comments</span></span>](./index.md)
