---
description: 'Más información acerca de: <paramref> (Visual Basic)'
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 0ce748213e26c258b290828c42454b0e7fd316f1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456840"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="e1020-102">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1020-102">\<paramref> (Visual Basic)</span></span>

<span data-ttu-id="e1020-103">Da formato a una palabra como parámetro.</span><span class="sxs-lookup"><span data-stu-id="e1020-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1020-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1020-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1020-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1020-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="e1020-106">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e1020-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="e1020-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="e1020-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1020-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1020-108">Remarks</span></span>  

 <span data-ttu-id="e1020-109">La `<paramref>` etiqueta le proporciona una forma de indicar que una palabra es un parámetro.</span><span class="sxs-lookup"><span data-stu-id="e1020-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="e1020-110">El archivo XML se puede procesar para dar formato a este parámetro de alguna manera distinta.</span><span class="sxs-lookup"><span data-stu-id="e1020-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="e1020-111">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="e1020-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1020-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1020-112">Example</span></span>  

 <span data-ttu-id="e1020-113">En este ejemplo se usa la `<paramref>` etiqueta para hacer referencia al `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e1020-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e1020-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1020-114">See also</span></span>

- [<span data-ttu-id="e1020-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="e1020-115">XML Comment Tags</span></span>](index.md)
