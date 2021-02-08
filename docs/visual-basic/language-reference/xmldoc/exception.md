---
description: 'Más información acerca de: <exception> (Visual Basic)'
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 14b7f78dd2521f7d5b3d62f635baa5b50969afa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787479"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="2395e-102">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2395e-102">\<exception> (Visual Basic)</span></span>

<span data-ttu-id="2395e-103">Especifica qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="2395e-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2395e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2395e-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2395e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2395e-105">Parameters</span></span>  

 `member`  
 <span data-ttu-id="2395e-106">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="2395e-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="2395e-107">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="2395e-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2395e-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="2395e-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2395e-109">Una descripción.</span><span class="sxs-lookup"><span data-stu-id="2395e-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2395e-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2395e-110">Remarks</span></span>  

 <span data-ttu-id="2395e-111">Use la `<exception>` etiqueta para especificar qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="2395e-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="2395e-112">Esta etiqueta se aplica a una definición de método.</span><span class="sxs-lookup"><span data-stu-id="2395e-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="2395e-113">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2395e-113">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2395e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2395e-114">Example</span></span>  

 <span data-ttu-id="2395e-115">En este ejemplo se usa la `<exception>` etiqueta para describir una excepción que la `IntDivide` función puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="2395e-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2395e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2395e-116">See also</span></span>

- [<span data-ttu-id="2395e-117">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="2395e-117">XML Comment Tags</span></span>](index.md)
