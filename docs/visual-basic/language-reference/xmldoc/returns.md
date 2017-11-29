---
title: '&lt;Devuelve&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6130a6fabe450900fe19ef4d361654508f907ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="40165-102">&lt;Devuelve&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40165-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="40165-103">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="40165-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40165-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40165-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40165-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40165-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="40165-106">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="40165-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40165-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40165-107">Remarks</span></span>  
 <span data-ttu-id="40165-108">Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="40165-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="40165-109">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="40165-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40165-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40165-110">Example</span></span>  
 <span data-ttu-id="40165-111">Este ejemplo se utiliza la `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.</span><span class="sxs-lookup"><span data-stu-id="40165-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="40165-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="40165-112">See Also</span></span>  
 [<span data-ttu-id="40165-113">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="40165-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
