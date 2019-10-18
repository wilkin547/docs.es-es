---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524633"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="522f0-102">\<summary > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="522f0-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="522f0-103">Especifica el resumen del miembro.</span><span class="sxs-lookup"><span data-stu-id="522f0-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="522f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="522f0-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="522f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="522f0-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="522f0-106">Resumen del objeto.</span><span class="sxs-lookup"><span data-stu-id="522f0-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="522f0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="522f0-107">Remarks</span></span>  
 <span data-ttu-id="522f0-108">Use la etiqueta `<summary>` para describir un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="522f0-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="522f0-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) para agregar información adicional a una descripción de tipo.</span><span class="sxs-lookup"><span data-stu-id="522f0-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="522f0-110">El texto de la etiqueta `<summary>` es el único origen de información sobre el tipo en IntelliSense y también se muestra en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="522f0-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="522f0-111">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="522f0-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="522f0-112">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="522f0-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="522f0-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="522f0-113">Example</span></span>  
 <span data-ttu-id="522f0-114">En este ejemplo se usa la etiqueta `<summary>` para describir el método `ResetCounter` y la propiedad `Counter`.</span><span class="sxs-lookup"><span data-stu-id="522f0-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="522f0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="522f0-115">See also</span></span>

- [<span data-ttu-id="522f0-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="522f0-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
