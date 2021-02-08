---
description: 'Más información acerca de: <c> (Visual Basic)'
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 350a5dbf2dee2911c356a7c76a9bafbab35fd71e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787518"
---
# <a name="c-visual-basic"></a><span data-ttu-id="b7318-102">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7318-102">\<c> (Visual Basic)</span></span>

<span data-ttu-id="b7318-103">Indica que el texto de una descripción es código.</span><span class="sxs-lookup"><span data-stu-id="b7318-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7318-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7318-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7318-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7318-105">Parameters</span></span>  
  
|<span data-ttu-id="b7318-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b7318-106">Parameter</span></span>|<span data-ttu-id="b7318-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7318-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="b7318-108">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="b7318-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7318-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7318-109">Remarks</span></span>  

 <span data-ttu-id="b7318-110">La etiqueta `<c>` le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="b7318-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="b7318-111">Use [\<code>](code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="b7318-111">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="b7318-112">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="b7318-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7318-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7318-113">Example</span></span>  

 <span data-ttu-id="b7318-114">En este ejemplo se usa la `<c>` etiqueta en la sección de resumen para indicar que `Counter` es código.</span><span class="sxs-lookup"><span data-stu-id="b7318-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b7318-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7318-115">See also</span></span>

- [<span data-ttu-id="b7318-116">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="b7318-116">XML Comment Tags</span></span>](index.md)
