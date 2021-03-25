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
ms.openlocfilehash: 379d3fda06c50e9e988784e671061d604e6e5b36
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477854"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="2d654-105">\<permission> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2d654-105">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d654-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d654-106">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="2d654-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d654-107">Parameters</span></span>

- <span data-ttu-id="2d654-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="2d654-108">cref = " `member`"</span></span>

  <span data-ttu-id="2d654-109">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="2d654-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="2d654-110">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="2d654-110">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2d654-111">*member* debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="2d654-111">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="2d654-112">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [Atributo cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="2d654-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="2d654-113">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="2d654-113">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d654-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d654-114">Remarks</span></span>

<span data-ttu-id="2d654-115">La etiqueta `<permission>` le permite documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="2d654-115">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="2d654-116">La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="2d654-116">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="2d654-117">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="2d654-117">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="2d654-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d654-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="2d654-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d654-119">See also</span></span>

- [<span data-ttu-id="2d654-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2d654-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="2d654-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="2d654-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
