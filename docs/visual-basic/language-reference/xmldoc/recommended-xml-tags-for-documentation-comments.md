---
title: "Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54712deb8bb2a5ed1e7b1f5fb8aa073dcdaf76d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="d10ec-102">Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ec-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="d10ec-103">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador puede procesar los comentarios de documentación en el código en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d10ec-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="d10ec-104">Puede utilizar herramientas adicionales para procesar el archivo XML en la documentación.</span><span class="sxs-lookup"><span data-stu-id="d10ec-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="d10ec-105">Comentarios XML están permitidos en construcciones de código, como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d10ec-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="d10ec-106">Para los tipos parciales, solo una parte del tipo puede tener comentarios XML, aunque no hay ninguna restricción sobre la creación de comentarios de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="d10ec-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d10ec-107">Los comentarios de documentación no se puede aplicar a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d10ec-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="d10ec-108">El motivo es que un espacio de nombres puede abarcar varios ensamblados y no todos los ensamblados tienen que cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d10ec-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="d10ec-109">El compilador procesa cualquier etiqueta XML válido.</span><span class="sxs-lookup"><span data-stu-id="d10ec-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="d10ec-110">Las siguientes etiquetas proporcionan funcionalidad utilizada en la documentación de usuario.</span><span class="sxs-lookup"><span data-stu-id="d10ec-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="d10ec-111">\<c></span><span class="sxs-lookup"><span data-stu-id="d10ec-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="d10ec-112">\<code></span><span class="sxs-lookup"><span data-stu-id="d10ec-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="d10ec-113">\<example></span><span class="sxs-lookup"><span data-stu-id="d10ec-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="d10ec-114">[\<excepción >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="d10ec-115">[\<Incluir >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="d10ec-116">\<list></span><span class="sxs-lookup"><span data-stu-id="d10ec-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="d10ec-117">\<para></span><span class="sxs-lookup"><span data-stu-id="d10ec-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="d10ec-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="d10ec-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="d10ec-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="d10ec-120">[\<permiso >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="d10ec-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="d10ec-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="d10ec-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="d10ec-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="d10ec-123">[\<Consulte >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="d10ec-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="d10ec-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="d10ec-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="d10ec-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d10ec-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="d10ec-127">\<value></span><span class="sxs-lookup"><span data-stu-id="d10ec-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="d10ec-128">(<sup>1</sup> el compilador comprueba la sintaxis.)</span><span class="sxs-lookup"><span data-stu-id="d10ec-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d10ec-129">Si desea que aparezcan en el texto de un comentario de documentación corchetes angulares, utilice `<` y `>`.</span><span class="sxs-lookup"><span data-stu-id="d10ec-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="d10ec-130">Por ejemplo, la cadena `"<text in angle brackets>"` aparecerá como `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="d10ec-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10ec-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d10ec-131">See Also</span></span>  
 [<span data-ttu-id="d10ec-132">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="d10ec-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="d10ec-133">/doc</span><span class="sxs-lookup"><span data-stu-id="d10ec-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="d10ec-134">Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="d10ec-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
