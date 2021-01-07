---
title: Errores y advertencias del compilador
description: Descripciones y soluciones de los errores y las advertencias que emite el compilador de F#
ms.date: 12/21/2019
ms.openlocfilehash: 58430297abe807027afdc52841d67d1233401ff1
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856125"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="bbc04-103">Mensajes del compilador de F#</span><span class="sxs-lookup"><span data-stu-id="bbc04-103">F# compiler messages</span></span>

<span data-ttu-id="bbc04-104">En esta sección se detallan los errores y las advertencias que el compilador de F# emite para ciertos constructores.</span><span class="sxs-lookup"><span data-stu-id="bbc04-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="bbc04-105">Para cambiar los conjuntos de errores predeterminados, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbc04-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="bbc04-106">Tratar las advertencias específicas como si fueran errores mediante el uso de la opción `-warnaserror+` del compilador.</span><span class="sxs-lookup"><span data-stu-id="bbc04-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="bbc04-107">Omitir las advertencias específicas mediante el uso de la opción `-nowarn` del compilador.</span><span class="sxs-lookup"><span data-stu-id="bbc04-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="bbc04-108">Si algún error o advertencia particular todavía no aparece registrado en esta sección:</span><span class="sxs-lookup"><span data-stu-id="bbc04-108">If a particular warning or error is not yet recorded in this section:</span></span>

- <span data-ttu-id="bbc04-109">Vaya al final de esta página y envíe comentarios al respecto con el número o el texto del error.</span><span class="sxs-lookup"><span data-stu-id="bbc04-109">Go to the end of this page and send feedback that includes the number or text of the error, or</span></span>
- <span data-ttu-id="bbc04-110">Agréguelo siguiendo las instrucciones que encontrará en [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/master/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) y abriendo una solicitud de incorporación de cambios relativa a este repositorio.</span><span class="sxs-lookup"><span data-stu-id="bbc04-110">Add it yourself by following the instructions in [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/master/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) and opening a pull request for this repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbc04-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbc04-111">See also</span></span>

- [<span data-ttu-id="bbc04-112">Opciones del compilador de F#</span><span class="sxs-lookup"><span data-stu-id="bbc04-112">F# Compiler Options</span></span>](../compiler-options.md)
