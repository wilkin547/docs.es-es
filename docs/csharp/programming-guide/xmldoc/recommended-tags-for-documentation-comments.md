---
title: 'Etiquetas recomendadas para comentarios de documentación: guía de programación de C#'
description: Aprenda sobre las etiquetas recomendadas para los comentarios de la documentación. Vea una lista de etiquetas recomendadas y examine los recursos adicionales disponibles.
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 65bca6f979c5ffd91507b571a4f049377315192d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381520"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="d4b08-104">Etiquetas recomendadas para comentarios de documentación (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d4b08-104">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="d4b08-105">El compilador de C# procesa los comentarios de documentación de su código y les aplica formato como XML en un archivo cuyo nombre especifica en la opción de línea de comandos **/doc**.</span><span class="sxs-lookup"><span data-stu-id="d4b08-105">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="d4b08-106">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="d4b08-106">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="d4b08-107">Las etiquetas se procesan en construcciones de código como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d4b08-107">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="d4b08-108">Los comentarios de documentación no pueden aplicarse en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d4b08-108">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="d4b08-109">El compilador procesará cualquier etiqueta que sea un XML válido.</span><span class="sxs-lookup"><span data-stu-id="d4b08-109">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="d4b08-110">Las siguientes etiquetas proporcionan funciones de uso general en la documentación de usuario.</span><span class="sxs-lookup"><span data-stu-id="d4b08-110">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="d4b08-111">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="d4b08-111">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
<span data-ttu-id="d4b08-112">(\* denota que el compilador comprueba la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="d4b08-112">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="d4b08-113">Si quiere que aparezcan corchetes angulares en el texto de un comentario de documentación, utilice la codificación HTML de `<` y `>`, que es `&lt;` y `&gt;` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d4b08-113">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="d4b08-114">Esta codificación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4b08-114">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="d4b08-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b08-115">See also</span></span>

- [<span data-ttu-id="d4b08-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d4b08-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="d4b08-117">-doc (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d4b08-117">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="d4b08-118">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="d4b08-118">XML documentation comments</span></span>](./index.md)
