---
description: 'Más información acerca de: <returns> (Visual Basic)'
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: ba5f1e231502a67e86ffbb92cf8868c3aecb05d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640386"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="4da8e-103">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4da8e-103">\<returns> (Visual Basic)</span></span>

<span data-ttu-id="4da8e-104">Especifica el valor devuelto de la propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="4da8e-104">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4da8e-105">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4da8e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4da8e-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="4da8e-107">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4da8e-107">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da8e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4da8e-108">Remarks</span></span>  

 <span data-ttu-id="4da8e-109">Use la `<returns>` etiqueta del comentario para una declaración de método para describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4da8e-109">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="4da8e-110">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4da8e-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da8e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4da8e-111">Example</span></span>  

 <span data-ttu-id="4da8e-112">En este ejemplo se usa la `<returns>` etiqueta para explicar lo que `DoesRecordExist` devuelve la función.</span><span class="sxs-lookup"><span data-stu-id="4da8e-112">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4da8e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da8e-113">See also</span></span>

- [<span data-ttu-id="4da8e-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="4da8e-114">XML Comment Tags</span></span>](index.md)
