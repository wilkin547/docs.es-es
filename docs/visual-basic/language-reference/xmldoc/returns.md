---
title: '&lt;Devuelve&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 4dcf8e9aee6edecbda2874a6e07fbe6e3772b18b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580530"
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="5a724-102">&lt;Devuelve&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a724-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="5a724-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="5a724-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a724-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a724-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a724-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a724-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5a724-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5a724-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a724-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a724-107">Remarks</span></span>  
 <span data-ttu-id="5a724-108">Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5a724-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="5a724-109">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="5a724-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a724-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a724-110">Example</span></span>  
 <span data-ttu-id="5a724-111">Este ejemplo se usa el `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.</span><span class="sxs-lookup"><span data-stu-id="5a724-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5a724-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a724-112">See also</span></span>
- [<span data-ttu-id="5a724-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="5a724-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
