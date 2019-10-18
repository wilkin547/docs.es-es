---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524608"
---
# <a name="value-visual-basic"></a><span data-ttu-id="c9c21-102">\<value > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9c21-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="c9c21-103">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c21-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9c21-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9c21-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9c21-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="c9c21-106">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c21-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9c21-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9c21-107">Remarks</span></span>  
 <span data-ttu-id="c9c21-108">Use la etiqueta `<value>` para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c21-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="c9c21-109">Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una \<summary etiqueta de [>](../../../visual-basic/language-reference/xmldoc/summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c21-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="c9c21-110">Después, debe agregar manualmente una etiqueta de `<value>` para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c21-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="c9c21-111">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="c9c21-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9c21-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9c21-112">Example</span></span>  
 <span data-ttu-id="c9c21-113">En este ejemplo se usa la etiqueta `<value>` para describir el valor que contiene la propiedad `Counter`.</span><span class="sxs-lookup"><span data-stu-id="c9c21-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c9c21-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9c21-114">See also</span></span>

- [<span data-ttu-id="c9c21-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="c9c21-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
