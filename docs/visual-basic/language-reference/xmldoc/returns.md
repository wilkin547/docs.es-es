---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 670064084d3297a54b2860da3fe3acab00fa3ed8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469188"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="e8618-102">\<Devuelve > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8618-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="e8618-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="e8618-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8618-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8618-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8618-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8618-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e8618-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e8618-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8618-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8618-107">Remarks</span></span>  
 <span data-ttu-id="e8618-108">Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e8618-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="e8618-109">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="e8618-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8618-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8618-110">Example</span></span>  
 <span data-ttu-id="e8618-111">Este ejemplo se usa el `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.</span><span class="sxs-lookup"><span data-stu-id="e8618-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e8618-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8618-112">See also</span></span>
- [<span data-ttu-id="e8618-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="e8618-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
