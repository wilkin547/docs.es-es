---
description: 'Más información sobre: etiquetas XML recomendadas para comentarios de documentación (Visual Basic)'
title: Etiquetas XML recomendadas para comentarios de documentación
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 5d3451d98b66817de143cfbddbcb6121de57ca8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787453"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="67dc0-103">Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67dc0-103">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>

<span data-ttu-id="67dc0-104">El compilador de Visual Basic puede procesar comentarios de documentación en el código en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="67dc0-104">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="67dc0-105">Puede usar herramientas adicionales para procesar el archivo XML en la documentación de.</span><span class="sxs-lookup"><span data-stu-id="67dc0-105">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="67dc0-106">Los comentarios XML se permiten en construcciones de código como tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="67dc0-106">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="67dc0-107">En el caso de los tipos parciales, solo una parte del tipo puede tener comentarios XML, aunque no hay ninguna restricción en el comentario de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="67dc0-107">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67dc0-108">Los comentarios de documentación no se pueden aplicar a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="67dc0-108">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="67dc0-109">La razón es que un espacio de nombres puede abarcar varios ensamblados, y no todos los ensamblados deben cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="67dc0-109">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="67dc0-110">El compilador procesa cualquier etiqueta que sea XML válida.</span><span class="sxs-lookup"><span data-stu-id="67dc0-110">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="67dc0-111">Las siguientes etiquetas proporcionan funcionalidad de uso común en la documentación del usuario.</span><span class="sxs-lookup"><span data-stu-id="67dc0-111">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="67dc0-112">[\<exception>](exception.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-112">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="67dc0-113">[\<include>](include.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-113">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="67dc0-114">[\<param>](param.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-114">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="67dc0-115">[\<permission>](permission.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-115">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="67dc0-116">[\<see>](see.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-116">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="67dc0-117">[\<seealso>](seealso.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-117">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="67dc0-118">[\<typeparam>](typeparam.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67dc0-118">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="67dc0-119">(<sup>1</sup> el compilador comprueba la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="67dc0-119">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67dc0-120">Si desea que los corchetes angulares aparezcan en el texto de un Comentario de documentación, use `&lt;` y `&gt;` .</span><span class="sxs-lookup"><span data-stu-id="67dc0-120">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="67dc0-121">Por ejemplo, la cadena `"&lt;text in angle brackets&gt;"` aparecerá como `<text in angle brackets>` .</span><span class="sxs-lookup"><span data-stu-id="67dc0-121">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dc0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="67dc0-122">See also</span></span>

- [<span data-ttu-id="67dc0-123">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="67dc0-123">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="67dc0-124">-doc</span><span class="sxs-lookup"><span data-stu-id="67dc0-124">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="67dc0-125">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="67dc0-125">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
