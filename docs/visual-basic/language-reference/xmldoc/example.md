---
title: '&lt;en el ejemplo se&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e34b75f4ce924a35dd5396b449730316025a9f35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltexamplegt-visual-basic"></a><span data-ttu-id="d0015-102">&lt;en el ejemplo se&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0015-102">&lt;example&gt; (Visual Basic)</span></span>
<span data-ttu-id="d0015-103">Especifica un ejemplo para el miembro.</span><span class="sxs-lookup"><span data-stu-id="d0015-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0015-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0015-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0015-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0015-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d0015-106">Una descripción del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="d0015-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0015-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0015-107">Remarks</span></span>  
 <span data-ttu-id="d0015-108">La `<example>` etiqueta le permite especificar un ejemplo de cómo utilizar un método u otro miembro de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d0015-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d0015-109">Esto normalmente implica el uso de la etiqueta [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="d0015-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="d0015-110">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="d0015-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0015-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0015-111">Example</span></span>  
 <span data-ttu-id="d0015-112">Este ejemplo se utiliza la `<example>` etiqueta para incluir un ejemplo para usar el `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="d0015-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d0015-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0015-113">See Also</span></span>  
 [<span data-ttu-id="d0015-114">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="d0015-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
