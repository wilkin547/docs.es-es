---
title: '&lt;paramref&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3bf3d4f04997a03f442cf7fd2a1586604198d3fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltparamrefgt-visual-basic"></a><span data-ttu-id="ebab1-102">&lt;paramref&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebab1-102">&lt;paramref&gt; (Visual Basic)</span></span>
<span data-ttu-id="ebab1-103">Da formato a una palabra como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="ebab1-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebab1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebab1-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebab1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebab1-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ebab1-106">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ebab1-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="ebab1-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ebab1-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebab1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebab1-108">Remarks</span></span>  
 <span data-ttu-id="ebab1-109">La `<paramref>` etiqueta ofrece una manera de indicar que una palabra es un parámetro.</span><span class="sxs-lookup"><span data-stu-id="ebab1-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="ebab1-110">El archivo XML se puede procesar para dar formato a este parámetro de algún modo diferente.</span><span class="sxs-lookup"><span data-stu-id="ebab1-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="ebab1-111">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="ebab1-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebab1-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebab1-112">Example</span></span>  
 <span data-ttu-id="ebab1-113">Este ejemplo se utiliza la `<paramref>` etiqueta para hacer referencia a la `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ebab1-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ebab1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebab1-114">See Also</span></span>  
 [<span data-ttu-id="ebab1-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="ebab1-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
