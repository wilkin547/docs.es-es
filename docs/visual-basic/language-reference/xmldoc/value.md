---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940743"
---
# <a name="value-visual-basic"></a><span data-ttu-id="8b86d-102">\<valor > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b86d-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="8b86d-103">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b86d-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b86d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b86d-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b86d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b86d-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8b86d-106">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b86d-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b86d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b86d-107">Remarks</span></span>  
 <span data-ttu-id="8b86d-108">Use el `<value>` etiquetas para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b86d-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="8b86d-109">Tenga en cuenta que cuando se agrega una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, agregará un [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b86d-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="8b86d-110">A continuación, debe agregar manualmente un `<value>` etiquetas para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b86d-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8b86d-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="8b86d-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b86d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b86d-112">Example</span></span>  
 <span data-ttu-id="8b86d-113">Este ejemplo se usa el `<value>` etiquetas para describir qué valor la `Counter` suspensiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b86d-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8b86d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b86d-114">See also</span></span>

- [<span data-ttu-id="8b86d-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="8b86d-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
