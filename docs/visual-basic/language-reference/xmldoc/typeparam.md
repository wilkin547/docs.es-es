---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: d362f181921a39d274eaee78e85976522ce4fc15
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863194"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="620a9-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="620a9-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="620a9-103">Define un nombre de parámetro de tipo y descripción.</span><span class="sxs-lookup"><span data-stu-id="620a9-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="620a9-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="620a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="620a9-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="620a9-106">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="620a9-106">The name of the type parameter.</span></span> <span data-ttu-id="620a9-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="620a9-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="620a9-108">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="620a9-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="620a9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="620a9-109">Remarks</span></span>  
 <span data-ttu-id="620a9-110">Use la `<typeparam>` etiqueta en el comentario de un tipo genérico o declaración de miembro genérico describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="620a9-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="620a9-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="620a9-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="620a9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="620a9-112">Example</span></span>  
 <span data-ttu-id="620a9-113">Este ejemplo se usa el `<typeparam>` etiquetas para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="620a9-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="620a9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="620a9-114">See Also</span></span>  
 [<span data-ttu-id="620a9-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="620a9-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
