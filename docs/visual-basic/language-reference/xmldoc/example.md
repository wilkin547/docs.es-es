---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: a1dea0bcc40de8dea986e93a25617f607383ec21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969224"
---
# <a name="example-visual-basic"></a><span data-ttu-id="d9d35-102">\<ejemplo > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d35-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="d9d35-103">Especifica un ejemplo para el miembro.</span><span class="sxs-lookup"><span data-stu-id="d9d35-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9d35-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9d35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9d35-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d9d35-106">Una descripción del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="d9d35-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9d35-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9d35-107">Remarks</span></span>  
 <span data-ttu-id="d9d35-108">El `<example>` etiqueta le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d9d35-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d9d35-109">Esto normalmente implica el uso de la etiqueta [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="d9d35-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="d9d35-110">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="d9d35-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9d35-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9d35-111">Example</span></span>  
 <span data-ttu-id="d9d35-112">Este ejemplo se usa el `<example>` etiqueta para incluir un ejemplo para usar el `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="d9d35-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d9d35-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9d35-113">See also</span></span>
- [<span data-ttu-id="d9d35-114">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="d9d35-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
