---
title: Punto de entrada (F#)
description: 'Obtenga información sobre cómo establecer el punto de entrada a un programa de F # que se compila como un archivo ejecutable, dónde formalmente comienza la ejecución.'
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "45698398"
---
# <a name="entry-point"></a><span data-ttu-id="93396-103">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="93396-103">Entry Point</span></span>

<span data-ttu-id="93396-104">Este tema describe el método que se utiliza para establecer el punto de entrada a un programa de F #.</span><span class="sxs-lookup"><span data-stu-id="93396-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="93396-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93396-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="93396-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93396-106">Remarks</span></span>

<span data-ttu-id="93396-107">En la sintaxis anterior, *enlace de función permiten* es la definición de una función en un `let` enlace.</span><span class="sxs-lookup"><span data-stu-id="93396-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="93396-108">El punto de entrada a un programa que se compila como un archivo ejecutable es dónde formalmente comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="93396-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="93396-109">Especificar el punto de entrada a una aplicación de F # aplicando el `EntryPoint` atributo para el programa `main` función.</span><span class="sxs-lookup"><span data-stu-id="93396-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="93396-110">Esta función (creada mediante un `let` enlace) debe ser la última función en el último archivo compilado.</span><span class="sxs-lookup"><span data-stu-id="93396-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="93396-111">El último archivo compilado es el último archivo del proyecto o el último archivo que se pasa a la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="93396-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="93396-112">La función de punto de entrada tiene el tipo `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="93396-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="93396-113">Los argumentos proporcionados en la línea de comandos se pasan a la `main` función en la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="93396-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="93396-114">El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="93396-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="93396-115">El valor devuelto se utiliza como el código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="93396-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="93396-116">Cero indica normalmente correctamente; valores distintos de cero indican un error.</span><span class="sxs-lookup"><span data-stu-id="93396-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="93396-117">No hay ninguna convención para el significado específico de los códigos de retorno distinto de cero; los significados de los códigos de retorno son específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93396-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="93396-118">El ejemplo siguiente muestra un sencillo `main` función.</span><span class="sxs-lookup"><span data-stu-id="93396-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="93396-119">Cuando se ejecuta este código con la línea de comandos `EntryPoint.exe 1 2 3`, el resultado es como sigue.</span><span class="sxs-lookup"><span data-stu-id="93396-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="93396-120">Punto de entrada implícito</span><span class="sxs-lookup"><span data-stu-id="93396-120">Implicit Entry Point</span></span>

<span data-ttu-id="93396-121">Cuando un programa no tiene ningún **EntryPoint** atributo que indica el punto de entrada, los enlaces de nivel superior en el último archivo para compilarse de forma explícita se utilizan como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="93396-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="93396-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="93396-122">See also</span></span>

- [<span data-ttu-id="93396-123">Funciones</span><span class="sxs-lookup"><span data-stu-id="93396-123">Functions</span></span>](index.md)
- [<span data-ttu-id="93396-124">Enlaces let</span><span class="sxs-lookup"><span data-stu-id="93396-124">let Bindings</span></span>](let-bindings.md)
