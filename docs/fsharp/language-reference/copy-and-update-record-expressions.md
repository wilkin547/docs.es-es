---
title: Expresiones de registro de copia y actualización
description: Obtenga información sobre cómo escribir una expresión ' copiar y actualizar ' que copie un registro existente o un registro anónimo, actualice los campos especificados y devuelva el registro actualizado o el registro anónimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630379"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="4bb31-103">Expresiones de registro de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="4bb31-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="4bb31-104">Una *expresión de registro de copia y actualización* es una expresión que copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.</span><span class="sxs-lookup"><span data-stu-id="4bb31-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="4bb31-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bb31-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="4bb31-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4bb31-106">Remarks</span></span>

<span data-ttu-id="4bb31-107">Los registros y los registros anónimos son inmutables de forma predeterminada, por lo que no se puede realizar ninguna actualización en un registro existente.</span><span class="sxs-lookup"><span data-stu-id="4bb31-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="4bb31-108">Para crear un registro actualizado, deben volver a especificarse todos los campos de un registro.</span><span class="sxs-lookup"><span data-stu-id="4bb31-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="4bb31-109">Para simplificar esta tarea, se puede usar una *expresión de copia y actualización* .</span><span class="sxs-lookup"><span data-stu-id="4bb31-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="4bb31-110">Esta expresión toma un registro existente, crea uno nuevo del mismo tipo usando los campos especificados de la expresión y el campo que falta especificado por la expresión.</span><span class="sxs-lookup"><span data-stu-id="4bb31-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="4bb31-111">Esto puede ser útil si tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de los campos.</span><span class="sxs-lookup"><span data-stu-id="4bb31-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="4bb31-112">Tome como ejemplo un registro recién creado.</span><span class="sxs-lookup"><span data-stu-id="4bb31-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="4bb31-113">Si solo se actualizara en el campo de ese registro, podría usar la *expresión de registro de copia y actualización* como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bb31-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="4bb31-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bb31-114">See also</span></span>

- [<span data-ttu-id="4bb31-115">Registros</span><span class="sxs-lookup"><span data-stu-id="4bb31-115">Records</span></span>](records.md)
- [<span data-ttu-id="4bb31-116">Registros anónimos</span><span class="sxs-lookup"><span data-stu-id="4bb31-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="4bb31-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="4bb31-117">F# Language Reference</span></span>](index.md)
