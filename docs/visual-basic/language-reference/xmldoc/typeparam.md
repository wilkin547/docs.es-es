---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 0a68cf0a495c2809961e8ec99effa459b0647fec
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866382"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="ef4d9-101">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef4d9-101">\<typeparam> (Visual Basic)</span></span>

<span data-ttu-id="ef4d9-102">Define un nombre de parámetro de tipo y una descripción.</span><span class="sxs-lookup"><span data-stu-id="ef4d9-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef4d9-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef4d9-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef4d9-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef4d9-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="ef4d9-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="ef4d9-105">The name of the type parameter.</span></span> <span data-ttu-id="ef4d9-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ef4d9-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ef4d9-107">Descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="ef4d9-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef4d9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef4d9-108">Remarks</span></span>  

 <span data-ttu-id="ef4d9-109">Use la `<typeparam>` etiqueta del comentario para un tipo genérico o una declaración de miembro genérico para describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="ef4d9-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="ef4d9-110">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ef4d9-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef4d9-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef4d9-111">Example</span></span>  

 <span data-ttu-id="ef4d9-112">En este ejemplo se usa la `<typeparam>` etiqueta para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ef4d9-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="ef4d9-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef4d9-113">See also</span></span>

- [<span data-ttu-id="ef4d9-114">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="ef4d9-114">XML Comment Tags</span></span>](index.md)
