---
title: '&lt;Devuelve&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 47debcef2c6ce56fda4c4a0818c8e813b41ebad1
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925023"
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="fb0ec-102">&lt;Devuelve&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb0ec-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="fb0ec-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="fb0ec-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb0ec-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb0ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb0ec-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="fb0ec-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="fb0ec-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb0ec-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb0ec-107">Remarks</span></span>  
 <span data-ttu-id="fb0ec-108">Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="fb0ec-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="fb0ec-109">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="fb0ec-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb0ec-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb0ec-110">Example</span></span>  
 <span data-ttu-id="fb0ec-111">Este ejemplo se usa el `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.</span><span class="sxs-lookup"><span data-stu-id="fb0ec-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fb0ec-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb0ec-112">See Also</span></span>  
 [<span data-ttu-id="fb0ec-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="fb0ec-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
