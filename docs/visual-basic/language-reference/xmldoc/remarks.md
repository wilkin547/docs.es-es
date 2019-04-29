---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c5c088472ae09a416953d9c0829cad1cb48646b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940821"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="b07bd-102">\<remarks > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b07bd-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="b07bd-103">Especifica una sección de comentarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="b07bd-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b07bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b07bd-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b07bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b07bd-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="b07bd-106">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="b07bd-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b07bd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b07bd-107">Remarks</span></span>  
 <span data-ttu-id="b07bd-108">Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementar la información especificada con [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="b07bd-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="b07bd-109">Esta información aparece en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="b07bd-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="b07bd-110">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="b07bd-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="b07bd-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="b07bd-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b07bd-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b07bd-112">Example</span></span>  
 <span data-ttu-id="b07bd-113">Este ejemplo se usa el `<remarks>` etiqueta para explicar qué es el `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="b07bd-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b07bd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b07bd-114">See also</span></span>

- [<span data-ttu-id="b07bd-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="b07bd-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
