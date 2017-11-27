---
title: Punto de entrada (F#)
description: "Obtenga información acerca de cómo establecer el punto de entrada a un programa de F # que se compila como un archivo ejecutable, dónde formalmente comienza la ejecución."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 91455443-ff9d-4510-a7e9-1560bdcd0bb0
ms.openlocfilehash: 685fd4da67119aa5fcaaffd142a0a17c8f5dc7f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="entry-point"></a><span data-ttu-id="20062-104">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="20062-104">Entry Point</span></span>

<span data-ttu-id="20062-105">Este tema describe el método que use para establecer el punto de entrada a un programa en F #.</span><span class="sxs-lookup"><span data-stu-id="20062-105">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="20062-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20062-106">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="20062-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20062-107">Remarks</span></span>
<span data-ttu-id="20062-108">En la sintaxis anterior, *enlace de función permiten* es la definición de una función en un `let` enlace.</span><span class="sxs-lookup"><span data-stu-id="20062-108">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="20062-109">El punto de entrada a un programa que se compila como un archivo ejecutable es dónde formalmente comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="20062-109">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="20062-110">Especifique el punto de entrada a una aplicación de F # aplicando la `EntryPoint` de atributo para el programa `main` función.</span><span class="sxs-lookup"><span data-stu-id="20062-110">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="20062-111">Esta función (creada mediante una `let` enlace) debe ser la última función del último archivo compilado.</span><span class="sxs-lookup"><span data-stu-id="20062-111">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="20062-112">El último archivo compilado es el último archivo de proyecto o el último archivo que se pasa a la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="20062-112">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="20062-113">La función de punto de entrada tiene el tipo `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="20062-113">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="20062-114">Los argumentos proporcionados en la línea de comandos se pasan a la `main` función en la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="20062-114">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="20062-115">El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="20062-115">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="20062-116">El valor devuelto se utiliza como el código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="20062-116">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="20062-117">Cero normalmente indica éxito; valores distintos de cero indican un error.</span><span class="sxs-lookup"><span data-stu-id="20062-117">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="20062-118">No hay ninguna convención para el significado específico de los códigos de retorno es distinto de cero; los significados de los códigos de retorno son específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="20062-118">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="20062-119">En el ejemplo siguiente se muestra un sencillo `main` función.</span><span class="sxs-lookup"><span data-stu-id="20062-119">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="20062-120">Cuando se ejecuta este código con la línea de comandos `EntryPoint.exe 1 2 3`, el resultado es como sigue.</span><span class="sxs-lookup"><span data-stu-id="20062-120">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="20062-121">Punto de entrada implícito</span><span class="sxs-lookup"><span data-stu-id="20062-121">Implicit Entry Point</span></span>
<span data-ttu-id="20062-122">Cuando un programa no tiene ningún **EntryPoint** atributo que indica el punto de entrada, los enlaces de nivel superior en el último archivo para compilarse de forma explícita se utilizan como el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="20062-122">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="20062-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="20062-123">See Also</span></span>
[<span data-ttu-id="20062-124">Funciones</span><span class="sxs-lookup"><span data-stu-id="20062-124">Functions</span></span>](index.md)

[<span data-ttu-id="20062-125">Enlaces let</span><span class="sxs-lookup"><span data-stu-id="20062-125">let Bindings</span></span>](let-bindings.md)
