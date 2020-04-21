---
title: Expresiones de registro de copia y actualización
description: Aprenda a escribir una "expresión de copia y actualización" que copie un registro existente o un registro anónimo, actualice los campos especificados y devuelva el registro actualizado o el registro anónimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739288"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="5f35b-103">Expresiones de registro de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="5f35b-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="5f35b-104">Una expresión de registro de *copia y actualización* es una expresión que copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.</span><span class="sxs-lookup"><span data-stu-id="5f35b-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f35b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f35b-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="5f35b-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f35b-106">Remarks</span></span>

<span data-ttu-id="5f35b-107">Los registros y registros anónimos son inmutables de forma predeterminada, por lo que no es posible actualizar un registro existente.</span><span class="sxs-lookup"><span data-stu-id="5f35b-107">Records and anonymous records are immutable by default, so it is not possible to update an existing record.</span></span> <span data-ttu-id="5f35b-108">Para crear un registro actualizado, todos los campos de un registro tendrían que especificarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5f35b-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="5f35b-109">Para simplificar esta tarea se puede utilizar una expresión de *copia y actualización.*</span><span class="sxs-lookup"><span data-stu-id="5f35b-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="5f35b-110">Esta expresión toma un registro existente, crea uno nuevo del mismo tipo mediante el uso de campos especificados de la expresión y el campo que falta especificado por la expresión.</span><span class="sxs-lookup"><span data-stu-id="5f35b-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="5f35b-111">Esto puede ser útil cuando tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de campo.</span><span class="sxs-lookup"><span data-stu-id="5f35b-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="5f35b-112">Tomemos por ejemplo un registro recién creado.</span><span class="sxs-lookup"><span data-stu-id="5f35b-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="5f35b-113">Para actualizar solo dos campos de ese registro, puede utilizar la expresión de *registro de copia y actualización:*</span><span class="sxs-lookup"><span data-stu-id="5f35b-113">To update only two fields in that record you can use the *copy and update record expression*:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="5f35b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f35b-114">See also</span></span>

- [<span data-ttu-id="5f35b-115">Registros</span><span class="sxs-lookup"><span data-stu-id="5f35b-115">Records</span></span>](records.md)
- [<span data-ttu-id="5f35b-116">Registros anónimos</span><span class="sxs-lookup"><span data-stu-id="5f35b-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="5f35b-117">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="5f35b-117">F# Language Reference</span></span>](index.md)
