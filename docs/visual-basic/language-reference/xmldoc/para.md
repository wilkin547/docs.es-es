---
title: '&lt;para&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2a034974ed94b18da374fbd372063ea4d575440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="72c51-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72c51-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="72c51-103">Especifica que el contenido es un formato como un párrafo.</span><span class="sxs-lookup"><span data-stu-id="72c51-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72c51-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72c51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72c51-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="72c51-106">El texto del párrafo.</span><span class="sxs-lookup"><span data-stu-id="72c51-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72c51-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72c51-107">Remarks</span></span>  
 <span data-ttu-id="72c51-108">El `<para>` etiqueta es para su uso dentro de una etiqueta, como [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<comentarios >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<devuelve >](../../../visual-basic/language-reference/xmldoc/returns.md), y le permite agregar estructura al texto.</span><span class="sxs-lookup"><span data-stu-id="72c51-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="72c51-109">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="72c51-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72c51-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72c51-110">Example</span></span>  
 <span data-ttu-id="72c51-111">Este ejemplo se utiliza la `<para>` etiqueta para dividir la sección Comentarios para el `UpdateRecord` método en dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="72c51-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="72c51-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="72c51-112">See Also</span></span>  
 [<span data-ttu-id="72c51-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="72c51-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
