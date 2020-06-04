---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411478"
---
# <a name="value-visual-basic"></a><span data-ttu-id="b84f1-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b84f1-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="b84f1-102">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b84f1-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84f1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b84f1-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b84f1-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b84f1-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="b84f1-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b84f1-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b84f1-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b84f1-106">Remarks</span></span>  
 <span data-ttu-id="b84f1-107">Use la `<value>` etiqueta para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b84f1-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="b84f1-108">Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una [\<summary>](summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="b84f1-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="b84f1-109">Después, debe agregar manualmente una `<value>` etiqueta para describir el valor que la propiedad representa.</span><span class="sxs-lookup"><span data-stu-id="b84f1-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="b84f1-110">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="b84f1-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b84f1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b84f1-111">Example</span></span>  
 <span data-ttu-id="b84f1-112">En este ejemplo se usa la `<value>` etiqueta para describir el valor que `Counter` contiene la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b84f1-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b84f1-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b84f1-113">See also</span></span>

- [<span data-ttu-id="b84f1-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="b84f1-114">XML Comment Tags</span></span>](index.md)
