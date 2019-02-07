---
title: <permission> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 4725e82c6b085e220f63346a8c6838ecc288efa1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263659"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="376f2-102">\<permission> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="376f2-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="376f2-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="376f2-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="376f2-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="376f2-104">Parameters</span></span>  
 <span data-ttu-id="376f2-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="376f2-105">cref = " `member`"</span></span>  
 <span data-ttu-id="376f2-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="376f2-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="376f2-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="376f2-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="376f2-108">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="376f2-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="376f2-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="376f2-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="376f2-110">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="376f2-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="376f2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="376f2-111">Remarks</span></span>  
 <span data-ttu-id="376f2-112">La etiqueta \<permission> le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="376f2-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="376f2-113">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="376f2-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="376f2-114">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="376f2-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="376f2-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="376f2-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="376f2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="376f2-116">See also</span></span>

- [<span data-ttu-id="376f2-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="376f2-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="376f2-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="376f2-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
