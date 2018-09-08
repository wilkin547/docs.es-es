---
title: Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 3b2dec4224006d35fb9add11e170b9dcbeeafcf3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44177836"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="23221-102">Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23221-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="23221-103">El compilador de Visual Basic puede procesar comentarios de documentación en el código en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="23221-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="23221-104">Puede usar herramientas adicionales para procesar el archivo XML en la documentación.</span><span class="sxs-lookup"><span data-stu-id="23221-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="23221-105">Los comentarios XML se permiten en construcciones de código, como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="23221-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="23221-106">Para los tipos parciales, sólo una parte del tipo puede tener comentarios XML, aunque no hay ninguna restricción sobre los comentarios de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="23221-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23221-107">Comentarios de documentación no se puede aplicar a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="23221-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="23221-108">El motivo es que un espacio de nombres puede abarcar varios ensamblados y no todos los ensamblados tienen que cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="23221-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="23221-109">El compilador procesa cualquier etiqueta válida en XML.</span><span class="sxs-lookup"><span data-stu-id="23221-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="23221-110">Las siguientes etiquetas proporcionan funcionalidad de uso común en la documentación de usuario.</span><span class="sxs-lookup"><span data-stu-id="23221-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="23221-111">\<c></span><span class="sxs-lookup"><span data-stu-id="23221-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="23221-112">\<code></span><span class="sxs-lookup"><span data-stu-id="23221-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="23221-113">\<example></span><span class="sxs-lookup"><span data-stu-id="23221-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="23221-114">[\<excepción >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="23221-115">[\<Incluir >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="23221-116">\<list></span><span class="sxs-lookup"><span data-stu-id="23221-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="23221-117">\<para></span><span class="sxs-lookup"><span data-stu-id="23221-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="23221-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="23221-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="23221-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="23221-120">[\<permiso >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="23221-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="23221-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="23221-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="23221-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="23221-123">[\<Consulte >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="23221-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="23221-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="23221-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="23221-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23221-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="23221-127">\<value></span><span class="sxs-lookup"><span data-stu-id="23221-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="23221-128">(<sup>1</sup> el compilador comprueba la sintaxis.)</span><span class="sxs-lookup"><span data-stu-id="23221-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23221-129">Si desea que aparezcan en el texto de un comentario de documentación corchetes angulares, utilice `&lt;` y `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="23221-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="23221-130">Por ejemplo, la cadena `"&lt;text in angle brackets&gt;"` aparecerá como `<text in angle brackets>`.</span><span class="sxs-lookup"><span data-stu-id="23221-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23221-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="23221-131">See Also</span></span>  
 [<span data-ttu-id="23221-132">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="23221-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="23221-133">/doc</span><span class="sxs-lookup"><span data-stu-id="23221-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="23221-134">Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="23221-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
