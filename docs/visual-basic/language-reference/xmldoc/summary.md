---
description: 'Más información acerca de: <summary> (Visual Basic)'
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 4d4b1ecf0fa054eb625c1a3cf09c1cab4e661ef2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640295"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="b6890-103">\<summary> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6890-103">\<summary> (Visual Basic)</span></span>

<span data-ttu-id="b6890-104">Especifica el resumen del miembro.</span><span class="sxs-lookup"><span data-stu-id="b6890-104">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6890-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6890-105">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6890-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6890-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="b6890-107">Resumen del objeto.</span><span class="sxs-lookup"><span data-stu-id="b6890-107">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6890-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6890-108">Remarks</span></span>  

 <span data-ttu-id="b6890-109">Use la `<summary>` etiqueta para describir un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="b6890-109">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="b6890-110">Use [\<remarks>](remarks.md) para agregar información adicional a una descripción de tipo.</span><span class="sxs-lookup"><span data-stu-id="b6890-110">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="b6890-111">El texto de la `<summary>` etiqueta es el único origen de información sobre el tipo en IntelliSense y también se muestra en el examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="b6890-111">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="b6890-112">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="b6890-112">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="b6890-113">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="b6890-113">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6890-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6890-114">Example</span></span>  

 <span data-ttu-id="b6890-115">En este ejemplo se usa la `<summary>` etiqueta para describir el `ResetCounter` método y la `Counter` propiedad.</span><span class="sxs-lookup"><span data-stu-id="b6890-115">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b6890-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6890-116">See also</span></span>

- [<span data-ttu-id="b6890-117">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="b6890-117">XML Comment Tags</span></span>](index.md)
