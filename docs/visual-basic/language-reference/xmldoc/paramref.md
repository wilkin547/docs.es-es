---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3ca08016d3cef0c44e4f3c0bd0d017628eda606d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400052"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="4076a-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4076a-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="4076a-102">Da formato a una palabra como parámetro.</span><span class="sxs-lookup"><span data-stu-id="4076a-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4076a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4076a-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4076a-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4076a-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4076a-105">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4076a-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="4076a-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="4076a-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4076a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4076a-107">Remarks</span></span>  
 <span data-ttu-id="4076a-108">La `<paramref>` etiqueta le proporciona una forma de indicar que una palabra es un parámetro.</span><span class="sxs-lookup"><span data-stu-id="4076a-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="4076a-109">El archivo XML se puede procesar para dar formato a este parámetro de alguna manera distinta.</span><span class="sxs-lookup"><span data-stu-id="4076a-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="4076a-110">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4076a-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4076a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4076a-111">Example</span></span>  
 <span data-ttu-id="4076a-112">En este ejemplo se usa la `<paramref>` etiqueta para hacer referencia al `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4076a-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4076a-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4076a-113">See also</span></span>

- [<span data-ttu-id="4076a-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="4076a-114">XML Comment Tags</span></span>](index.md)
