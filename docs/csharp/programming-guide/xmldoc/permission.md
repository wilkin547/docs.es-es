---
title: <permission> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 14abb5bd181f401a4e6834d110e20fa920566580
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789733"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="e53f8-102">\<permission> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e53f8-102">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="e53f8-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e53f8-103">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="e53f8-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e53f8-104">Parameters</span></span>

- <span data-ttu-id="e53f8-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="e53f8-105">cref = " `member`"</span></span>

  <span data-ttu-id="e53f8-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="e53f8-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e53f8-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="e53f8-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e53f8-108">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="e53f8-108">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="e53f8-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="e53f8-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>

- `description`

  <span data-ttu-id="e53f8-110">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="e53f8-110">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="e53f8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e53f8-111">Remarks</span></span>

<span data-ttu-id="e53f8-112">La etiqueta \<permission> le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="e53f8-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="e53f8-113">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="e53f8-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="e53f8-114">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="e53f8-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="e53f8-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e53f8-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="e53f8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e53f8-116">See also</span></span>

- [<span data-ttu-id="e53f8-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e53f8-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e53f8-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="e53f8-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
