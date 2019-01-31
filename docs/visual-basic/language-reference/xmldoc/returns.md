---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 0463d1b489fdad5e6af2d8eb20a1e68c77f57b4d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254969"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="acc8a-102">\<Devuelve > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acc8a-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="acc8a-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="acc8a-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acc8a-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acc8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acc8a-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="acc8a-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="acc8a-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acc8a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acc8a-107">Remarks</span></span>  
 <span data-ttu-id="acc8a-108">Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="acc8a-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="acc8a-109">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="acc8a-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acc8a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acc8a-110">Example</span></span>  
 <span data-ttu-id="acc8a-111">Este ejemplo se usa el `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.</span><span class="sxs-lookup"><span data-stu-id="acc8a-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="acc8a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="acc8a-112">See also</span></span>
- [<span data-ttu-id="acc8a-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="acc8a-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
