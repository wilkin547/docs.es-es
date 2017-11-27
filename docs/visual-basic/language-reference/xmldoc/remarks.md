---
title: '&lt;comentarios&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f70c2d7df190d2ff8187882a9176dbe98984296
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="fe14c-102">&lt;comentarios&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe14c-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="fe14c-103">Especifica una sección de comentarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="fe14c-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe14c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe14c-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe14c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe14c-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="fe14c-106">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="fe14c-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe14c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe14c-107">Remarks</span></span>  
 <span data-ttu-id="fe14c-108">Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementando la información especificada con [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="fe14c-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="fe14c-109">Esta información aparece en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="fe14c-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="fe14c-110">Para obtener información sobre el Examinador de objetos, consulte [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="fe14c-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="fe14c-111">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="fe14c-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe14c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe14c-112">Example</span></span>  
 <span data-ttu-id="fe14c-113">Este ejemplo se utiliza la `<remarks>` etiqueta para explicar qué es el `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="fe14c-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fe14c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe14c-114">See Also</span></span>  
 [<span data-ttu-id="fe14c-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="fe14c-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
