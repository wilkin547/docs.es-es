---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872701"
---
# <a name="para-visual-basic"></a><span data-ttu-id="3bb6f-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bb6f-101">\<para> (Visual Basic)</span></span>

<span data-ttu-id="3bb6f-102">Especifica que el contenido está formateado como un párrafo.</span><span class="sxs-lookup"><span data-stu-id="3bb6f-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb6f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bb6f-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bb6f-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bb6f-104">Parameters</span></span>  

 `content`  
 <span data-ttu-id="3bb6f-105">El texto del párrafo.</span><span class="sxs-lookup"><span data-stu-id="3bb6f-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bb6f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3bb6f-106">Remarks</span></span>  

 <span data-ttu-id="3bb6f-107">La etiqueta `<para>` se usa dentro de otra etiqueta, como [\<summary>](summary.md), [\<remarks>](remarks.md) o [\<returns>](returns.md), y permite dar una estructura al texto.</span><span class="sxs-lookup"><span data-stu-id="3bb6f-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="3bb6f-108">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="3bb6f-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bb6f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bb6f-109">Example</span></span>  

 <span data-ttu-id="3bb6f-110">En este ejemplo se usa la `<para>` etiqueta para dividir la sección Comentarios del `UpdateRecord` método en dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="3bb6f-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3bb6f-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bb6f-111">See also</span></span>

- [<span data-ttu-id="3bb6f-112">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="3bb6f-112">XML Comment Tags</span></span>](index.md)
