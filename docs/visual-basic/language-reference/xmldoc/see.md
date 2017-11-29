---
title: '&lt;consulte&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 010a3403d7748653648b323ad07f52bf93db2879
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="0f93f-102">&lt;consulte&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f93f-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="0f93f-103">Especifica un vínculo a otro miembro.</span><span class="sxs-lookup"><span data-stu-id="0f93f-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f93f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f93f-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f93f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f93f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="0f93f-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="0f93f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="0f93f-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="0f93f-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="0f93f-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="0f93f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f93f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f93f-109">Remarks</span></span>  
 <span data-ttu-id="0f93f-110">Use la `<see>` etiqueta para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="0f93f-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="0f93f-111">Use [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) para indicar el texto que desea que aparezca en una sección "Vea también".</span><span class="sxs-lookup"><span data-stu-id="0f93f-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="0f93f-112">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="0f93f-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f93f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f93f-113">Example</span></span>  
 <span data-ttu-id="0f93f-114">Este ejemplo se utiliza la `<see>` etiqueta en el `UpdateRecord` remarks sección para hacer referencia a la `DoesRecordExist` método.</span><span class="sxs-lookup"><span data-stu-id="0f93f-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0f93f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f93f-115">See Also</span></span>  
 [<span data-ttu-id="0f93f-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="0f93f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
