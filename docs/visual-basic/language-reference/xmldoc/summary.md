---
title: '&lt;resumen&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 5ef9b7a98503ff36174de4418ca7d599c365f5aa
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869810"
---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="6f0e3-102">&lt;resumen&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f0e3-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="6f0e3-103">Especifica el resumen del miembro.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f0e3-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f0e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f0e3-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="6f0e3-106">Resumen del objeto.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f0e3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f0e3-107">Remarks</span></span>  
 <span data-ttu-id="6f0e3-108">Use el `<summary>` etiquetas para describir un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="6f0e3-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) para agregar información adicional a una descripción de tipo.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="6f0e3-110">El texto para el `<summary>` etiqueta es la única fuente de información sobre el tipo en IntelliSense y también se muestra en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="6f0e3-111">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="6f0e3-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="6f0e3-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f0e3-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f0e3-113">Example</span></span>  
 <span data-ttu-id="6f0e3-114">Este ejemplo se usa el `<summary>` etiquetas para describir el `ResetCounter` método y `Counter` propiedad.</span><span class="sxs-lookup"><span data-stu-id="6f0e3-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6f0e3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f0e3-115">See Also</span></span>  
 [<span data-ttu-id="6f0e3-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="6f0e3-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
