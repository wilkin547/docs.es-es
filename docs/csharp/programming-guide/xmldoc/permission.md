---
title: '&lt;permission&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 815d303c9cfbf01588f5f2877e9f87a7ebbea9a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321482"
---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="87a00-102">&lt;permission&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="87a00-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="87a00-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87a00-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87a00-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87a00-104">Parameters</span></span>  
 <span data-ttu-id="87a00-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="87a00-105">cref = " `member`"</span></span>  
 <span data-ttu-id="87a00-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="87a00-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="87a00-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="87a00-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="87a00-108">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="87a00-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="87a00-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="87a00-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="87a00-110">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="87a00-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87a00-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87a00-111">Remarks</span></span>  
 <span data-ttu-id="87a00-112">La etiqueta \<permission> le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="87a00-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="87a00-113">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="87a00-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="87a00-114">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="87a00-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a00-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87a00-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="87a00-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="87a00-116">See Also</span></span>  
 [<span data-ttu-id="87a00-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="87a00-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="87a00-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="87a00-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
