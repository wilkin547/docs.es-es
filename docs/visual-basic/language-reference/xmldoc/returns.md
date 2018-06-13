---
title: '&lt;Devuelve&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: effc55bd65ae6c54575b7931529499505a9523cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598370"
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="b9f76-102">&lt;Devuelve&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9f76-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="b9f76-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="b9f76-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9f76-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9f76-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9f76-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="b9f76-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b9f76-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9f76-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9f76-107">Remarks</span></span>  
 <span data-ttu-id="b9f76-108">Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b9f76-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="b9f76-109">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="b9f76-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9f76-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9f76-110">Example</span></span>  
 <span data-ttu-id="b9f76-111">Este ejemplo se utiliza la `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.</span><span class="sxs-lookup"><span data-stu-id="b9f76-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b9f76-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9f76-112">See Also</span></span>  
 [<span data-ttu-id="b9f76-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="b9f76-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
