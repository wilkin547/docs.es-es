---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 89a2daad1c47ea8e2a045b2e22a9569e54086e8a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970745"
---
# <a name="value-visual-basic"></a><span data-ttu-id="f9045-102">\<valor > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9045-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="f9045-103">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9045-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9045-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9045-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9045-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9045-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="f9045-106">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9045-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9045-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9045-107">Remarks</span></span>  
 <span data-ttu-id="f9045-108">Use el `<value>` etiquetas para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9045-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="f9045-109">Tenga en cuenta que cuando se agrega una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, agregará un [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9045-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="f9045-110">A continuación, debe agregar manualmente un `<value>` etiquetas para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9045-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="f9045-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="f9045-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9045-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9045-112">Example</span></span>  
 <span data-ttu-id="f9045-113">Este ejemplo se usa el `<value>` etiquetas para describir qué valor la `Counter` suspensiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9045-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f9045-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9045-114">See also</span></span>
- [<span data-ttu-id="f9045-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="f9045-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
