---
description: 'Más información acerca de: <para> (Visual Basic)'
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 51dd9ff300d980b4c0576566cad5d17375889ba1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740774"
---
# <a name="para-visual-basic"></a><span data-ttu-id="281a2-103">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="281a2-103">\<para> (Visual Basic)</span></span>

<span data-ttu-id="281a2-104">Especifica que el contenido está formateado como un párrafo.</span><span class="sxs-lookup"><span data-stu-id="281a2-104">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281a2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="281a2-105">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="281a2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="281a2-106">Parameters</span></span>  

 `content`  
 <span data-ttu-id="281a2-107">El texto del párrafo.</span><span class="sxs-lookup"><span data-stu-id="281a2-107">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="281a2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="281a2-108">Remarks</span></span>  

 <span data-ttu-id="281a2-109">La etiqueta `<para>` se usa dentro de otra etiqueta, como [\<summary>](summary.md), [\<remarks>](remarks.md) o [\<returns>](returns.md), y permite dar una estructura al texto.</span><span class="sxs-lookup"><span data-stu-id="281a2-109">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="281a2-110">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="281a2-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="281a2-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="281a2-111">Example</span></span>  

 <span data-ttu-id="281a2-112">En este ejemplo se usa la `<para>` etiqueta para dividir la sección Comentarios del `UpdateRecord` método en dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="281a2-112">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="281a2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="281a2-113">See also</span></span>

- [<span data-ttu-id="281a2-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="281a2-114">XML Comment Tags</span></span>](index.md)
