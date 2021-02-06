---
description: 'Más información acerca de: <value> (Visual Basic)'
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 80a3ef875eea4418d28d60dac1818f3390c361ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640256"
---
# <a name="value-visual-basic"></a><span data-ttu-id="9a20b-103">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a20b-103">\<value> (Visual Basic)</span></span>

<span data-ttu-id="9a20b-104">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a20b-104">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a20b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a20b-105">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a20b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a20b-106">Parameters</span></span>  

 `property-description`  
 <span data-ttu-id="9a20b-107">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a20b-107">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a20b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a20b-108">Remarks</span></span>  

 <span data-ttu-id="9a20b-109">Use la `<value>` etiqueta para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a20b-109">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="9a20b-110">Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una [\<summary>](summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a20b-110">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="9a20b-111">Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a20b-111">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="9a20b-112">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="9a20b-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a20b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a20b-113">Example</span></span>  

 <span data-ttu-id="9a20b-114">En este ejemplo se usa la `<value>` etiqueta para describir el valor que `Counter` contiene la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a20b-114">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9a20b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a20b-115">See also</span></span>

- [<span data-ttu-id="9a20b-116">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="9a20b-116">XML Comment Tags</span></span>](index.md)
