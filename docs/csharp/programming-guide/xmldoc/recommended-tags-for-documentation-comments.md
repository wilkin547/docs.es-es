---
title: Etiquetas recomendadas para comentarios de documentación (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: ef7ba44c0c3a8c660df9627361eb1cabdd9098a0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43741951"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="303fc-102">Etiquetas recomendadas para comentarios de documentación (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="303fc-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="303fc-103">El compilador de C# procesa los comentarios de documentación de su código y les aplica formato como XML en un archivo cuyo nombre especifica en la opción de línea de comandos **/doc**.</span><span class="sxs-lookup"><span data-stu-id="303fc-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="303fc-104">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="303fc-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="303fc-105">Las etiquetas se procesan en construcciones de código como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="303fc-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="303fc-106">Los comentarios de documentación no pueden aplicarse en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="303fc-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="303fc-107">El compilador procesará cualquier etiqueta que sea un XML válido.</span><span class="sxs-lookup"><span data-stu-id="303fc-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="303fc-108">Las siguientes etiquetas proporcionan funciones de uso general en la documentación de usuario.</span><span class="sxs-lookup"><span data-stu-id="303fc-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="303fc-109">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="303fc-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="303fc-110">\<c></span><span class="sxs-lookup"><span data-stu-id="303fc-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="303fc-111">\<para></span><span class="sxs-lookup"><span data-stu-id="303fc-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="303fc-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span></span>|  
|[<span data-ttu-id="303fc-113">\<code></span><span class="sxs-lookup"><span data-stu-id="303fc-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="303fc-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span></span>|<span data-ttu-id="303fc-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span></span>|  
|[<span data-ttu-id="303fc-116">\<example></span><span class="sxs-lookup"><span data-stu-id="303fc-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="303fc-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="303fc-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="303fc-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="303fc-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="303fc-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span></span>|<span data-ttu-id="303fc-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span></span>|<span data-ttu-id="303fc-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span></span>|  
|<span data-ttu-id="303fc-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span><span class="sxs-lookup"><span data-stu-id="303fc-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span></span>|[<span data-ttu-id="303fc-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="303fc-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="303fc-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="303fc-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="303fc-125">\<list></span><span class="sxs-lookup"><span data-stu-id="303fc-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="303fc-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="303fc-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="303fc-127">\<value></span><span class="sxs-lookup"><span data-stu-id="303fc-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="303fc-128">(\* denota que el compilador comprueba la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="303fc-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="303fc-129">Si quiere que aparezcan corchetes angulares en el texto de un comentario de documentación, use `<` y `>`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="303fc-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="303fc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="303fc-130">See Also</span></span>

- [<span data-ttu-id="303fc-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="303fc-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="303fc-132">/doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="303fc-132">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
- [<span data-ttu-id="303fc-133">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="303fc-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
