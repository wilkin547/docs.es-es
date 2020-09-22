---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872977"
---
# <a name="example-visual-basic"></a><span data-ttu-id="d11cf-101">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d11cf-101">\<example> (Visual Basic)</span></span>

<span data-ttu-id="d11cf-102">Especifica un ejemplo para el miembro.</span><span class="sxs-lookup"><span data-stu-id="d11cf-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11cf-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d11cf-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d11cf-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d11cf-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="d11cf-105">Una descripción del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="d11cf-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d11cf-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d11cf-106">Remarks</span></span>  

 <span data-ttu-id="d11cf-107">La etiqueta `<example>` le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d11cf-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d11cf-108">Esto normalmente implica el uso de la etiqueta [\<code>](code.md).</span><span class="sxs-lookup"><span data-stu-id="d11cf-108">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="d11cf-109">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="d11cf-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d11cf-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d11cf-110">Example</span></span>  

 <span data-ttu-id="d11cf-111">En este ejemplo se usa la `<example>` etiqueta para incluir un ejemplo de uso del `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="d11cf-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d11cf-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d11cf-112">See also</span></span>

- [<span data-ttu-id="d11cf-113">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="d11cf-113">XML Comment Tags</span></span>](index.md)
