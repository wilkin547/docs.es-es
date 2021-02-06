---
description: 'Más información acerca de: <typeparam> (Visual Basic)'
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: efb4394ee2badcf52bac75d7d9e317c732789746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640269"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="f8949-103">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8949-103">\<typeparam> (Visual Basic)</span></span>

<span data-ttu-id="f8949-104">Define un nombre de parámetro de tipo y una descripción.</span><span class="sxs-lookup"><span data-stu-id="f8949-104">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8949-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8949-105">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8949-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8949-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="f8949-107">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="f8949-107">The name of the type parameter.</span></span> <span data-ttu-id="f8949-108">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="f8949-108">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f8949-109">Descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="f8949-109">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8949-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8949-110">Remarks</span></span>  

 <span data-ttu-id="f8949-111">Use la `<typeparam>` etiqueta del comentario para un tipo genérico o una declaración de miembro genérico para describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="f8949-111">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="f8949-112">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="f8949-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8949-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8949-113">Example</span></span>  

 <span data-ttu-id="f8949-114">En este ejemplo se usa la `<typeparam>` etiqueta para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f8949-114">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="f8949-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8949-115">See also</span></span>

- [<span data-ttu-id="f8949-116">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="f8949-116">XML Comment Tags</span></span>](index.md)
