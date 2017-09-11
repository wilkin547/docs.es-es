---
title: "&lt;permission&gt; (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
dev_langs:
- CSharp
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b8f109d7e01f6e630f09939161b6a20c3a13f73
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="b51f5-102">&lt;permission&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b51f5-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b51f5-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b51f5-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b51f5-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b51f5-104">Parameters</span></span>  
 <span data-ttu-id="b51f5-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="b51f5-105">cref = " `member`"</span></span>  
 <span data-ttu-id="b51f5-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="b51f5-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b51f5-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="b51f5-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b51f5-108">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="b51f5-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="b51f5-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="b51f5-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="b51f5-110">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="b51f5-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b51f5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b51f5-111">Remarks</span></span>  
 <span data-ttu-id="b51f5-112">La etiqueta \<permission> le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="b51f5-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="b51f5-113">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="b51f5-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="b51f5-114">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="b51f5-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b51f5-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b51f5-115">Example</span></span>  
 <span data-ttu-id="b51f5-116">[!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b51f5-116">[!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51f5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b51f5-117">See Also</span></span>  
 <span data-ttu-id="b51f5-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b51f5-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b51f5-119">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="b51f5-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

