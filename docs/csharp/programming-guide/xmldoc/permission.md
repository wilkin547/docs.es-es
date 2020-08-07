---
title: <permission> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <permission> . Esta etiqueta le permite documentar el acceso de un miembro, mientras que la clase PermissionSet permite especificar el acceso a un miembro.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381728"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="ac9d4-105">\<permission> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ac9d4-105">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac9d4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac9d4-106">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="ac9d4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac9d4-107">Parameters</span></span>

- <span data-ttu-id="ac9d4-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="ac9d4-108">cref = " `member`"</span></span>

  <span data-ttu-id="ac9d4-109">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="ac9d4-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ac9d4-110">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="ac9d4-110">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="ac9d4-111">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ac9d4-111">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="ac9d4-112">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [Atributo cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="ac9d4-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="ac9d4-113">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="ac9d4-113">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac9d4-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac9d4-114">Remarks</span></span>

<span data-ttu-id="ac9d4-115">La etiqueta `<permission>` le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="ac9d4-115">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="ac9d4-116">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="ac9d4-116">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="ac9d4-117">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ac9d4-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ac9d4-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac9d4-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="ac9d4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac9d4-119">See also</span></span>

- [<span data-ttu-id="ac9d4-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ac9d4-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ac9d4-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ac9d4-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
