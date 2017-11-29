---
title: "&lt;excepción&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d718a7c2213a61f7f60ed80a04f9bd03f6c770a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="cbd8e-102">&lt;excepción&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbd8e-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="cbd8e-103">Especifica qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbd8e-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbd8e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cbd8e-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="cbd8e-106">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="cbd8e-107">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="cbd8e-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="cbd8e-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="cbd8e-109">Una descripción.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbd8e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbd8e-110">Remarks</span></span>  
 <span data-ttu-id="cbd8e-111">Use la `<exception>` etiqueta para especificar qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="cbd8e-112">Esta etiqueta se aplica a una definición de método.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="cbd8e-113">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbd8e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbd8e-114">Example</span></span>  
 <span data-ttu-id="cbd8e-115">Este ejemplo se utiliza la `<exception>` etiquetas para describir una excepción que el `IntDivide` función puede producir.</span><span class="sxs-lookup"><span data-stu-id="cbd8e-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cbd8e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbd8e-116">See Also</span></span>  
 [<span data-ttu-id="cbd8e-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="cbd8e-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
