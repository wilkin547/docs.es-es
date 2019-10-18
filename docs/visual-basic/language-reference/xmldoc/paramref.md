---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 85171bd8deeb5f54c4560bb8b2339107bb8d8c68
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524713"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="63ef9-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63ef9-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="63ef9-103">Da formato a una palabra como parámetro.</span><span class="sxs-lookup"><span data-stu-id="63ef9-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ef9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63ef9-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="63ef9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63ef9-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="63ef9-106">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="63ef9-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="63ef9-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="63ef9-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ef9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63ef9-108">Remarks</span></span>  
 <span data-ttu-id="63ef9-109">La etiqueta `<paramref>` proporciona una manera de indicar que una palabra es un parámetro.</span><span class="sxs-lookup"><span data-stu-id="63ef9-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="63ef9-110">El archivo XML se puede procesar para dar formato a este parámetro de alguna manera distinta.</span><span class="sxs-lookup"><span data-stu-id="63ef9-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="63ef9-111">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="63ef9-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63ef9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63ef9-112">Example</span></span>  
 <span data-ttu-id="63ef9-113">En este ejemplo se usa la etiqueta `<paramref>` para hacer referencia al parámetro `id`.</span><span class="sxs-lookup"><span data-stu-id="63ef9-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="63ef9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ef9-114">See also</span></span>

- [<span data-ttu-id="63ef9-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="63ef9-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
