---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 240c2131179420834e6dade729ee631c0d7811a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352170"
---
# <a name="value-visual-basic"></a><span data-ttu-id="38636-101">> de valor \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38636-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="38636-102">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="38636-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38636-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38636-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="38636-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38636-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="38636-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="38636-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38636-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38636-106">Remarks</span></span>  
 <span data-ttu-id="38636-107">Use la etiqueta `<value>` para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="38636-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="38636-108">Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una etiqueta [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="38636-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="38636-109">Después, debe agregar manualmente una etiqueta de `<value>` para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="38636-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="38636-110">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="38636-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38636-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38636-111">Example</span></span>  
 <span data-ttu-id="38636-112">En este ejemplo se usa la etiqueta `<value>` para describir el valor que contiene la propiedad `Counter`.</span><span class="sxs-lookup"><span data-stu-id="38636-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="38636-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38636-113">See also</span></span>

- [<span data-ttu-id="38636-114">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="38636-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
