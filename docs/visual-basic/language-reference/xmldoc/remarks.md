---
description: 'Más información acerca de: <remarks> (Visual Basic)'
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 4b0584abbe85a7ecc73e25dd1f6ec321962b88a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640412"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="fa5de-103">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa5de-103">\<remarks> (Visual Basic)</span></span>

<span data-ttu-id="fa5de-104">Especifica una sección de comentarios para el miembro.</span><span class="sxs-lookup"><span data-stu-id="fa5de-104">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa5de-105">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa5de-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa5de-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="fa5de-107">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="fa5de-107">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa5de-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa5de-108">Remarks</span></span>  

 <span data-ttu-id="fa5de-109">Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementando la información especificada con [\<summary>](summary.md) .</span><span class="sxs-lookup"><span data-stu-id="fa5de-109">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](summary.md).</span></span>  
  
 <span data-ttu-id="fa5de-110">Esta información aparece en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="fa5de-110">This information appears in the Object Browser.</span></span> <span data-ttu-id="fa5de-111">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="fa5de-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="fa5de-112">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="fa5de-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa5de-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa5de-113">Example</span></span>  

 <span data-ttu-id="fa5de-114">En este ejemplo se usa la `<remarks>` etiqueta para explicar lo que `UpdateRecord` hace el método.</span><span class="sxs-lookup"><span data-stu-id="fa5de-114">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="fa5de-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa5de-115">See also</span></span>

- [<span data-ttu-id="fa5de-116">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="fa5de-116">XML Comment Tags</span></span>](index.md)
