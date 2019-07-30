---
title: Punto de entrada
description: Obtenga información sobre cómo establecer el punto de entrada F# en un programa que se compila como un archivo ejecutable, donde la ejecución se inicia formalmente.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630519"
---
# <a name="entry-point"></a><span data-ttu-id="ae80f-103">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="ae80f-103">Entry Point</span></span>

<span data-ttu-id="ae80f-104">En este tema se describe el método que se usa para establecer el punto de F# entrada en un programa.</span><span class="sxs-lookup"><span data-stu-id="ae80f-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae80f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae80f-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="ae80f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae80f-106">Remarks</span></span>

<span data-ttu-id="ae80f-107">En la sintaxis anterior, *Let-function-Binding* es la definición de una función en un `let` enlace.</span><span class="sxs-lookup"><span data-stu-id="ae80f-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="ae80f-108">El punto de entrada a un programa que se compila como un archivo ejecutable es donde se inicia la ejecución formalmente.</span><span class="sxs-lookup"><span data-stu-id="ae80f-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="ae80f-109">Para especificar el punto de entrada a F# una aplicación, aplique `EntryPoint` el atributo a la función `main` del programa.</span><span class="sxs-lookup"><span data-stu-id="ae80f-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="ae80f-110">Esta función (creada mediante un `let` enlace) debe ser la última función del último archivo compilado.</span><span class="sxs-lookup"><span data-stu-id="ae80f-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="ae80f-111">El último archivo compilado es el último archivo del proyecto o el último archivo que se pasa a la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ae80f-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="ae80f-112">La función de punto de entrada `string array -> int`tiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="ae80f-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="ae80f-113">Los argumentos proporcionados en la línea de comandos se pasan `main` a la función en la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="ae80f-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="ae80f-114">El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="ae80f-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="ae80f-115">El valor devuelto se usa como código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="ae80f-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="ae80f-116">Cero suele indicar Success; los valores distintos de cero indican un error.</span><span class="sxs-lookup"><span data-stu-id="ae80f-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="ae80f-117">No hay ninguna Convención para el significado específico de códigos de retorno distintos de cero; los significados de los códigos de retorno son específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae80f-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="ae80f-118">En el ejemplo siguiente se muestra una `main` función simple.</span><span class="sxs-lookup"><span data-stu-id="ae80f-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="ae80f-119">Cuando este código se ejecuta con la línea `EntryPoint.exe 1 2 3`de comandos, el resultado es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="ae80f-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="ae80f-120">Punto de entrada implícito</span><span class="sxs-lookup"><span data-stu-id="ae80f-120">Implicit Entry Point</span></span>

<span data-ttu-id="ae80f-121">Cuando un programa no tiene ningún atributo **EntryPoint** que indique explícitamente el punto de entrada, los enlaces de nivel superior del último archivo que se va a compilar se usan como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="ae80f-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae80f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae80f-122">See also</span></span>

- [<span data-ttu-id="ae80f-123">Funciones</span><span class="sxs-lookup"><span data-stu-id="ae80f-123">Functions</span></span>](index.md)
- [<span data-ttu-id="ae80f-124">Enlaces let</span><span class="sxs-lookup"><span data-stu-id="ae80f-124">let Bindings</span></span>](let-bindings.md)
