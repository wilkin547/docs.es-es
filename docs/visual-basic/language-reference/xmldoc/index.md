---
title: Etiquetas XML recomendadas para comentarios de documentación
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: af57fc7d55c5cfda24a2fd9406b17dedee898760
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400103"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="55d5d-102">Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55d5d-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="55d5d-103">El compilador de Visual Basic puede procesar comentarios de documentación en el código en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="55d5d-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="55d5d-104">Puede usar herramientas adicionales para procesar el archivo XML en la documentación de.</span><span class="sxs-lookup"><span data-stu-id="55d5d-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="55d5d-105">Los comentarios XML se permiten en construcciones de código como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="55d5d-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="55d5d-106">En el caso de los tipos parciales, solo una parte del tipo puede tener comentarios XML, aunque no hay ninguna restricción en el comentario de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="55d5d-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55d5d-107">Los comentarios de documentación no se pueden aplicar a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="55d5d-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="55d5d-108">La razón es que un espacio de nombres puede abarcar varios ensamblados, y no todos los ensamblados deben cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="55d5d-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="55d5d-109">El compilador procesa cualquier etiqueta que sea XML válida.</span><span class="sxs-lookup"><span data-stu-id="55d5d-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="55d5d-110">Las siguientes etiquetas proporcionan funcionalidad de uso común en la documentación del usuario.</span><span class="sxs-lookup"><span data-stu-id="55d5d-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="55d5d-111">[\<exception>](exception.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-111">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="55d5d-112">[\<include>](include.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-112">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="55d5d-113">[\<param>](param.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-113">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="55d5d-114">[\<permission>](permission.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-114">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="55d5d-115">[\<see>](see.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-115">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="55d5d-116">[\<seealso>](seealso.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-116">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="55d5d-117">[\<typeparam>](typeparam.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55d5d-117">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="55d5d-118">(<sup>1</sup> el compilador comprueba la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="55d5d-118">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55d5d-119">Si desea que los corchetes angulares aparezcan en el texto de un Comentario de documentación, use `&lt;` y `&gt;` .</span><span class="sxs-lookup"><span data-stu-id="55d5d-119">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="55d5d-120">Por ejemplo, la cadena `"&lt;text in angle brackets&gt;"` aparecerá como `<text in angle brackets>` .</span><span class="sxs-lookup"><span data-stu-id="55d5d-120">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d5d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="55d5d-121">See also</span></span>

- [<span data-ttu-id="55d5d-122">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="55d5d-122">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="55d5d-123">-doc</span><span class="sxs-lookup"><span data-stu-id="55d5d-123">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="55d5d-124">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="55d5d-124">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
