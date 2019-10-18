---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524739"
---
# <a name="para-visual-basic"></a><span data-ttu-id="07ece-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07ece-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="07ece-103">Especifica que el contenido está formateado como un párrafo.</span><span class="sxs-lookup"><span data-stu-id="07ece-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ece-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07ece-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="07ece-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07ece-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="07ece-106">El texto del párrafo.</span><span class="sxs-lookup"><span data-stu-id="07ece-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07ece-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07ece-107">Remarks</span></span>  
 <span data-ttu-id="07ece-108">La etiqueta `<para>` es para su uso dentro de una etiqueta, como [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md)o [\<returns > y](../../../visual-basic/language-reference/xmldoc/returns.md)permite agregar la estructura al texto.</span><span class="sxs-lookup"><span data-stu-id="07ece-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="07ece-109">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="07ece-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07ece-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07ece-110">Example</span></span>  
 <span data-ttu-id="07ece-111">En este ejemplo se usa la etiqueta `<para>` para dividir la sección Comentarios para el método `UpdateRecord` en dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="07ece-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="07ece-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="07ece-112">See also</span></span>

- [<span data-ttu-id="07ece-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="07ece-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
