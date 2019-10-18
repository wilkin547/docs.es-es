---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524682"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="4ce84-102">\<returns > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ce84-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="4ce84-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="4ce84-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ce84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ce84-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ce84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ce84-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="4ce84-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4ce84-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ce84-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ce84-107">Remarks</span></span>  
 <span data-ttu-id="4ce84-108">Use la etiqueta `<returns>` del comentario para una declaración de método que describa el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4ce84-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="4ce84-109">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4ce84-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ce84-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ce84-110">Example</span></span>  
 <span data-ttu-id="4ce84-111">En este ejemplo se usa la etiqueta `<returns>` para explicar lo que devuelve la función `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="4ce84-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4ce84-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ce84-112">See also</span></span>

- [<span data-ttu-id="4ce84-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="4ce84-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
