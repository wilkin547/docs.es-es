---
title: Errores y advertencias del compilador
description: Descripciones y soluciones de los errores y las advertencias que emite el compilador de F#
ms.date: 12/21/2019
ms.openlocfilehash: 9769ddee989f0774cfae8842e60dbd3fd2065f9c
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190182"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="9a78b-103">Mensajes del compilador de F#</span><span class="sxs-lookup"><span data-stu-id="9a78b-103">F# compiler messages</span></span>

<span data-ttu-id="9a78b-104">En esta sección se detallan los errores y las advertencias que el compilador de F# emite para ciertos constructores.</span><span class="sxs-lookup"><span data-stu-id="9a78b-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="9a78b-105">Para cambiar los conjuntos de errores predeterminados, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a78b-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="9a78b-106">Tratar las advertencias específicas como si fueran errores mediante el uso de la opción `-warnaserror+` del compilador.</span><span class="sxs-lookup"><span data-stu-id="9a78b-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="9a78b-107">Omitir las advertencias específicas mediante el uso de la opción `-nowarn` del compilador.</span><span class="sxs-lookup"><span data-stu-id="9a78b-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="9a78b-108">Si algún error o advertencia particular todavía no aparece registrado en esta sección:</span><span class="sxs-lookup"><span data-stu-id="9a78b-108">If a particular warning or error is not yet recorded in this section:</span></span>

- <span data-ttu-id="9a78b-109">Vaya al final de esta página y envíe comentarios al respecto con el número o el texto del error.</span><span class="sxs-lookup"><span data-stu-id="9a78b-109">Go to the end of this page and send feedback that includes the number or text of the error, or</span></span>
- <span data-ttu-id="9a78b-110">Agréguelo siguiendo las instrucciones que encontrará en [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/main/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) y abriendo una solicitud de incorporación de cambios relativa a este repositorio.</span><span class="sxs-lookup"><span data-stu-id="9a78b-110">Add it yourself by following the instructions in [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/main/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) and opening a pull request for this repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a78b-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a78b-111">See also</span></span>

- [<span data-ttu-id="9a78b-112">Opciones del compilador de F#</span><span class="sxs-lookup"><span data-stu-id="9a78b-112">F# Compiler Options</span></span>](../compiler-options.md)
