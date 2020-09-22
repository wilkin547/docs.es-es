---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 37b110cc6e12f11196d2a1c5cc6026d87b453626
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866409"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="52353-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52353-101">\<returns> (Visual Basic)</span></span>

<span data-ttu-id="52353-102">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="52353-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52353-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52353-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="52353-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52353-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="52353-105">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="52353-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52353-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52353-106">Remarks</span></span>  

 <span data-ttu-id="52353-107">Use la `<returns>` etiqueta del comentario para una declaración de método para describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="52353-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="52353-108">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="52353-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52353-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52353-109">Example</span></span>  

 <span data-ttu-id="52353-110">En este ejemplo se usa la `<returns>` etiqueta para explicar lo que `DoesRecordExist` devuelve la función.</span><span class="sxs-lookup"><span data-stu-id="52353-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="52353-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52353-111">See also</span></span>

- [<span data-ttu-id="52353-112">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="52353-112">XML Comment Tags</span></span>](index.md)
