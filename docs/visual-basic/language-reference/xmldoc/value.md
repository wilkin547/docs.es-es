---
title: '&lt;valor&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: ef14836c438cf6a1de300270d9882c1e53e716ee
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855938"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="6a249-102">&lt;valor&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a249-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="6a249-103">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a249-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a249-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a249-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a249-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a249-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="6a249-106">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a249-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a249-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a249-107">Remarks</span></span>  
 <span data-ttu-id="6a249-108">Use el `<value>` etiquetas para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a249-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="6a249-109">Tenga en cuenta que cuando se agrega una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, agregará un [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a249-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="6a249-110">A continuación, debe agregar manualmente un `<value>` etiquetas para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a249-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="6a249-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="6a249-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a249-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a249-112">Example</span></span>  
 <span data-ttu-id="6a249-113">Este ejemplo se usa el `<value>` etiquetas para describir qué valor la `Counter` suspensiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a249-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6a249-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a249-114">See Also</span></span>  
 [<span data-ttu-id="6a249-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="6a249-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
