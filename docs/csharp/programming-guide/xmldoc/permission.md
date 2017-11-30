---
title: "&lt;permission&gt; (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37bb37ea14edc1f91225f9b04b18b354d99579b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="0a87d-102">&lt;permission&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0a87d-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="0a87d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a87d-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a87d-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a87d-104">Parameters</span></span>  
 <span data-ttu-id="0a87d-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="0a87d-105">cref = " `member`"</span></span>  
 <span data-ttu-id="0a87d-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="0a87d-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="0a87d-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="0a87d-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="0a87d-108">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="0a87d-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="0a87d-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="0a87d-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="0a87d-110">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="0a87d-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a87d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a87d-111">Remarks</span></span>  
 <span data-ttu-id="0a87d-112">La etiqueta \<permission> le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="0a87d-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="0a87d-113">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="0a87d-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="0a87d-114">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="0a87d-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a87d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a87d-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0a87d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a87d-116">See Also</span></span>  
 [<span data-ttu-id="0a87d-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0a87d-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0a87d-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="0a87d-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
