---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400026"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="d929e-101">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d929e-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="d929e-102">Especifica una sección de comentarios para el miembro.</span><span class="sxs-lookup"><span data-stu-id="d929e-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d929e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d929e-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d929e-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d929e-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d929e-105">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="d929e-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d929e-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d929e-106">Remarks</span></span>  
 <span data-ttu-id="d929e-107">Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementando la información especificada con [\<summary>](summary.md) .</span><span class="sxs-lookup"><span data-stu-id="d929e-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](summary.md).</span></span>  
  
 <span data-ttu-id="d929e-108">Esta información aparece en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="d929e-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="d929e-109">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="d929e-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="d929e-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="d929e-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d929e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d929e-111">Example</span></span>  
 <span data-ttu-id="d929e-112">En este ejemplo se usa la `<remarks>` etiqueta para explicar lo que `UpdateRecord` hace el método.</span><span class="sxs-lookup"><span data-stu-id="d929e-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d929e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d929e-113">See also</span></span>

- [<span data-ttu-id="d929e-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="d929e-114">XML Comment Tags</span></span>](index.md)
