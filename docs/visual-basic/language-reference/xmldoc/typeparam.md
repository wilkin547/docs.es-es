---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: f84a5194551a718ff4ca512839a937f786740ca9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259233"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="cb85c-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb85c-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="cb85c-103">Define un nombre de parámetro de tipo y descripción.</span><span class="sxs-lookup"><span data-stu-id="cb85c-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb85c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb85c-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb85c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb85c-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cb85c-106">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cb85c-106">The name of the type parameter.</span></span> <span data-ttu-id="cb85c-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="cb85c-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="cb85c-108">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cb85c-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb85c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb85c-109">Remarks</span></span>  
 <span data-ttu-id="cb85c-110">Use la `<typeparam>` etiqueta en el comentario de un tipo genérico o declaración de miembro genérico describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="cb85c-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="cb85c-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="cb85c-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb85c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb85c-112">Example</span></span>  
 <span data-ttu-id="cb85c-113">Este ejemplo se usa el `<typeparam>` etiquetas para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="cb85c-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cb85c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb85c-114">See also</span></span>
- [<span data-ttu-id="cb85c-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="cb85c-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
