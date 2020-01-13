---
title: 'Etiquetas recomendadas para comentarios de documentación: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 15a183d72a7d3e47f99227cea2cf870ad2f98d18
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696537"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="63099-102">Etiquetas recomendadas para comentarios de documentación (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="63099-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="63099-103">El compilador de C# procesa los comentarios de documentación de su código y les aplica formato como XML en un archivo cuyo nombre especifica en la opción de línea de comandos **/doc**.</span><span class="sxs-lookup"><span data-stu-id="63099-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="63099-104">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="63099-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="63099-105">Las etiquetas se procesan en construcciones de código como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="63099-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63099-106">Los comentarios de documentación no pueden aplicarse en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63099-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="63099-107">El compilador procesará cualquier etiqueta que sea un XML válido.</span><span class="sxs-lookup"><span data-stu-id="63099-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="63099-108">Las siguientes etiquetas proporcionan funciones de uso general en la documentación de usuario.</span><span class="sxs-lookup"><span data-stu-id="63099-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="63099-109">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="63099-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="63099-110">\<c></span><span class="sxs-lookup"><span data-stu-id="63099-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="63099-111">\<para></span><span class="sxs-lookup"><span data-stu-id="63099-111">\<para></span></span>](./para.md)|<span data-ttu-id="63099-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="63099-113">\<code></span><span class="sxs-lookup"><span data-stu-id="63099-113">\<code></span></span>](./code.md)|<span data-ttu-id="63099-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="63099-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="63099-116">\<example></span><span class="sxs-lookup"><span data-stu-id="63099-116">\<example></span></span>](./example.md)|[<span data-ttu-id="63099-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="63099-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="63099-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="63099-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="63099-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="63099-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="63099-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="63099-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="63099-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="63099-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="63099-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="63099-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="63099-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="63099-125">\<list></span><span class="sxs-lookup"><span data-stu-id="63099-125">\<list></span></span>](./list.md)|[<span data-ttu-id="63099-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="63099-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="63099-127">\<value></span><span class="sxs-lookup"><span data-stu-id="63099-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="63099-128">(\* denota que el compilador comprueba la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="63099-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="63099-129">Si quiere que aparezcan corchetes angulares en el texto de un comentario de documentación, utilice la codificación HTML de `<` y `>`, que es `&lt;` y `&gt;` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="63099-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="63099-130">Esta codificación se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63099-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="63099-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="63099-131">See also</span></span>

- [<span data-ttu-id="63099-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="63099-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="63099-133">-doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="63099-133">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="63099-134">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="63099-134">XML Documentation Comments</span></span>](./index.md)
