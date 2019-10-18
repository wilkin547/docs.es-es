---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524669"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="cc19f-102">\<remarks > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc19f-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="cc19f-103">Especifica una sección de comentarios para el miembro.</span><span class="sxs-lookup"><span data-stu-id="cc19f-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc19f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc19f-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc19f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc19f-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="cc19f-106">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="cc19f-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc19f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc19f-107">Remarks</span></span>  
 <span data-ttu-id="cc19f-108">Use la etiqueta `<remarks>` para agregar información sobre un tipo, complementando la información especificada con [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="cc19f-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="cc19f-109">Esta información aparece en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="cc19f-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="cc19f-110">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="cc19f-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="cc19f-111">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="cc19f-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc19f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc19f-112">Example</span></span>  
 <span data-ttu-id="cc19f-113">En este ejemplo se usa la etiqueta `<remarks>` para explicar lo que hace el método `UpdateRecord`.</span><span class="sxs-lookup"><span data-stu-id="cc19f-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="cc19f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc19f-114">See also</span></span>

- [<span data-ttu-id="cc19f-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="cc19f-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
