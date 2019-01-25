---
title: '&lt;valor&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 92c8c2ac7b95e97b37c907e3837bc90dac384b33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558948"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="ff6c1-102">&lt;valor&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff6c1-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="ff6c1-103">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff6c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff6c1-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff6c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff6c1-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="ff6c1-106">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff6c1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff6c1-107">Remarks</span></span>  
 <span data-ttu-id="ff6c1-108">Use el `<value>` etiquetas para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="ff6c1-109">Tenga en cuenta que cuando se agrega una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, agregará un [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="ff6c1-110">A continuación, debe agregar manualmente un `<value>` etiquetas para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="ff6c1-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff6c1-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff6c1-112">Example</span></span>  
 <span data-ttu-id="ff6c1-113">Este ejemplo se usa el `<value>` etiquetas para describir qué valor la `Counter` suspensiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff6c1-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ff6c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff6c1-114">See also</span></span>
- [<span data-ttu-id="ff6c1-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="ff6c1-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
