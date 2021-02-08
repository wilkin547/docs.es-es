---
description: 'Más información acerca de: <example> (Visual Basic)'
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 643e06fd24e38123dd2693d671b9ab33da5b413e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787492"
---
# <a name="example-visual-basic"></a><span data-ttu-id="db6df-103">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db6df-103">\<example> (Visual Basic)</span></span>

<span data-ttu-id="db6df-104">Especifica un ejemplo para el miembro.</span><span class="sxs-lookup"><span data-stu-id="db6df-104">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6df-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db6df-105">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="db6df-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db6df-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="db6df-107">Una descripción del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="db6df-107">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db6df-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db6df-108">Remarks</span></span>  

 <span data-ttu-id="db6df-109">La etiqueta `<example>` le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="db6df-109">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="db6df-110">Esto normalmente implica el uso de la etiqueta [\<code>](code.md).</span><span class="sxs-lookup"><span data-stu-id="db6df-110">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="db6df-111">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="db6df-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db6df-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db6df-112">Example</span></span>  

 <span data-ttu-id="db6df-113">En este ejemplo se usa la `<example>` etiqueta para incluir un ejemplo de uso del `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="db6df-113">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="db6df-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db6df-114">See also</span></span>

- [<span data-ttu-id="db6df-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="db6df-115">XML Comment Tags</span></span>](index.md)
