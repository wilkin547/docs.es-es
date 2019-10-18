---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: dbd99997fed33c192a2160fb45a739addbae254a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524623"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="38a77-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38a77-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="38a77-103">Define un nombre de parámetro de tipo y una descripción.</span><span class="sxs-lookup"><span data-stu-id="38a77-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38a77-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="38a77-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38a77-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="38a77-106">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="38a77-106">The name of the type parameter.</span></span> <span data-ttu-id="38a77-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="38a77-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="38a77-108">Descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="38a77-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38a77-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38a77-109">Remarks</span></span>  
 <span data-ttu-id="38a77-110">Use la etiqueta `<typeparam>` del comentario para un tipo genérico o una declaración de miembro genérico para describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="38a77-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="38a77-111">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="38a77-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38a77-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38a77-112">Example</span></span>  
 <span data-ttu-id="38a77-113">En este ejemplo se usa la etiqueta `<typeparam>` para describir el parámetro `id`.</span><span class="sxs-lookup"><span data-stu-id="38a77-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="38a77-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="38a77-114">See also</span></span>

- [<span data-ttu-id="38a77-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="38a77-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
