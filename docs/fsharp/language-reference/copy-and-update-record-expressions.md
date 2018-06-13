---
title: 'Copiar y actualizar registros expresiones (F #)'
description: Obtenga información acerca de cómo escribir un 'copiar y actualizar registro expression' que copia las actualizaciones de registros, existente especificado campos y devuelve el registro actualizado.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 000746b6e76349ae6d8f338519a58034f4e29020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563064"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="53e1b-103">Expresiones de registro de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="53e1b-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="53e1b-104">A *copiar y actualizar registro expresión* es una expresión que copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.</span><span class="sxs-lookup"><span data-stu-id="53e1b-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="53e1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53e1b-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="53e1b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53e1b-106">Remarks</span></span>
<span data-ttu-id="53e1b-107">Los registros son inmutables de forma predeterminada, por lo que no es posible ninguna actualización para un registro existente.</span><span class="sxs-lookup"><span data-stu-id="53e1b-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="53e1b-108">Para crear un registro actualizado todos los campos de un registro que puede especificar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="53e1b-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="53e1b-109">Para simplificar esta tarea un *copiar y actualizar registro expresión* se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="53e1b-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="53e1b-110">Esta expresión toma un registro existente, crea una nueva del mismo tipo con campos especificados de la expresión y el especificado por la expresión de campo que no existe.</span><span class="sxs-lookup"><span data-stu-id="53e1b-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="53e1b-111">Esto puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo.</span><span class="sxs-lookup"><span data-stu-id="53e1b-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="53e1b-112">Tomemos como ejemplo un registro recién creado.</span><span class="sxs-lookup"><span data-stu-id="53e1b-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="53e1b-113">Si desea actualizar solo en el campo de ese registro podría utilizar el *copiar y actualizar registro expresión* como lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53e1b-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="53e1b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="53e1b-114">See Also</span></span>
[<span data-ttu-id="53e1b-115">Registros</span><span class="sxs-lookup"><span data-stu-id="53e1b-115">Records</span></span>](records.md)

[<span data-ttu-id="53e1b-116">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="53e1b-116">F# Language Reference</span></span>](index.md)
