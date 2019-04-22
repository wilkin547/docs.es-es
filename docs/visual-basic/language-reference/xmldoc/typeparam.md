---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 014623be84f9d7eb8a25ac4aadcce450f158c154
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827242"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="f6f5a-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f5a-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="f6f5a-103">Define un nombre de parámetro de tipo y descripción.</span><span class="sxs-lookup"><span data-stu-id="f6f5a-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6f5a-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6f5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6f5a-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f6f5a-106">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="f6f5a-106">The name of the type parameter.</span></span> <span data-ttu-id="f6f5a-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="f6f5a-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f6f5a-108">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="f6f5a-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6f5a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6f5a-109">Remarks</span></span>  
 <span data-ttu-id="f6f5a-110">Use la `<typeparam>` etiqueta en el comentario de un tipo genérico o declaración de miembro genérico describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="f6f5a-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="f6f5a-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="f6f5a-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f5a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6f5a-112">Example</span></span>  
 <span data-ttu-id="f6f5a-113">Este ejemplo se usa el `<typeparam>` etiquetas para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f6f5a-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="f6f5a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6f5a-114">See also</span></span>

- [<span data-ttu-id="f6f5a-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="f6f5a-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
