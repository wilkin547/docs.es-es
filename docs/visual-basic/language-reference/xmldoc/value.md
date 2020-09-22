---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 550f8b63928f80878ba316bfaf09077e14091305
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875171"
---
# <a name="value-visual-basic"></a><span data-ttu-id="05363-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05363-101">\<value> (Visual Basic)</span></span>

<span data-ttu-id="05363-102">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="05363-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05363-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05363-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="05363-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05363-104">Parameters</span></span>  

 `property-description`  
 <span data-ttu-id="05363-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="05363-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05363-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05363-106">Remarks</span></span>  

 <span data-ttu-id="05363-107">Use la `<value>` etiqueta para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="05363-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="05363-108">Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una [\<summary>](summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="05363-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="05363-109">Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="05363-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="05363-110">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="05363-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05363-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05363-111">Example</span></span>  

 <span data-ttu-id="05363-112">En este ejemplo se usa la `<value>` etiqueta para describir el valor que `Counter` contiene la propiedad.</span><span class="sxs-lookup"><span data-stu-id="05363-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="05363-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05363-113">See also</span></span>

- [<span data-ttu-id="05363-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="05363-114">XML Comment Tags</span></span>](index.md)
