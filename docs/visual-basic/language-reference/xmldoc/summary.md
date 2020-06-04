---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411504"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="c9cbb-101">\<summary> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9cbb-101">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="c9cbb-102">Especifica el resumen del miembro.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cbb-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9cbb-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9cbb-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9cbb-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c9cbb-105">Resumen del objeto.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9cbb-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c9cbb-106">Remarks</span></span>  
 <span data-ttu-id="c9cbb-107">Use la `<summary>` etiqueta para describir un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="c9cbb-108">Use [\<remarks>](remarks.md) para agregar información adicional a una descripción de tipo.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="c9cbb-109">El texto de la `<summary>` etiqueta es el único origen de información sobre el tipo en IntelliSense y también se muestra en el examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="c9cbb-110">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="c9cbb-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="c9cbb-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9cbb-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9cbb-112">Example</span></span>  
 <span data-ttu-id="c9cbb-113">En este ejemplo se usa la `<summary>` etiqueta para describir el `ResetCounter` método y la `Counter` propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9cbb-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c9cbb-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9cbb-114">See also</span></span>

- [<span data-ttu-id="c9cbb-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="c9cbb-115">XML Comment Tags</span></span>](index.md)
