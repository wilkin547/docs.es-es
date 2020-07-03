---
title: Ensamblados de múltiples archivos
description: Use ensamblados de varios archivos destinados a .NET mediante compiladores de línea de comandos o Visual Studio con Visual C++. Un archivo del ensamblado debe contener el manifiesto del ensamblado.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: a5fb41b3b136a325e6b8658da521cba3176e929f
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104633"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="56305-104">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="56305-104">Multifile assemblies</span></span>

<span data-ttu-id="56305-105">Puede crear ensamblados de varios archivos que tengan como destino .NET Framework mediante compiladores de línea de comandos o Visual Studio con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="56305-105">You can create multifile assemblies that target the .NET Framework using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="56305-106">Un archivo del ensamblado debe contener el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="56305-106">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="56305-107">Los ensamblados que inicien una aplicación también deben contener un punto de entrada, como un método `Main` o `WinMain`.</span><span class="sxs-lookup"><span data-stu-id="56305-107">An assembly that starts an application must also contain an entry point, such as a `Main` or `WinMain` method.</span></span>

<span data-ttu-id="56305-108">Por ejemplo, supongamos que tiene una aplicación que contiene dos módulos de código, *Client.cs* y *Stringer.cs*.</span><span class="sxs-lookup"><span data-stu-id="56305-108">For example, suppose you have an application that contains two code modules, *Client.cs* and *Stringer.cs*.</span></span> <span data-ttu-id="56305-109">*Stringer.cs* crea el espacio de nombres `myStringer` al que hace referencia el código de *Client.cs*.</span><span class="sxs-lookup"><span data-stu-id="56305-109">*Stringer.cs* creates the `myStringer` namespace that is referenced by the code in *Client.cs*.</span></span> <span data-ttu-id="56305-110">*Client.cs* contiene el método `Main`, que es el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="56305-110">*Client.cs* contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="56305-111">En este ejemplo, se compilan los dos módulos de código y, después, se crea un tercer archivo que contiene el manifiesto del ensamblado, que inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="56305-111">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="56305-112">El manifiesto del ensamblado hace referencia a los módulos *Client* y *Stringer*.</span><span class="sxs-lookup"><span data-stu-id="56305-112">The assembly manifest references both the *Client* and *Stringer* modules.</span></span>

> [!NOTE]
> <span data-ttu-id="56305-113">Los ensamblados de varios archivos pueden tener un único punto de entrada, incluso si el ensamblado tiene varios módulos de código.</span><span class="sxs-lookup"><span data-stu-id="56305-113">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="56305-114">Hay varias razones por las que le puede interesar crear un ensamblado de varios archivos:</span><span class="sxs-lookup"><span data-stu-id="56305-114">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="56305-115">Para combinar módulos escritos en lenguajes diferentes.</span><span class="sxs-lookup"><span data-stu-id="56305-115">To combine modules written in different languages.</span></span> <span data-ttu-id="56305-116">Esta es la razón más común para crear un ensamblado de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="56305-116">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="56305-117">Para optimizar la descarga de una aplicación al colocar los tipos menos usados en un módulo que solo se descarga cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="56305-117">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56305-118">Si va a crear aplicaciones que se descargarán mediante la etiqueta `<object>` con Microsoft Internet Explorer, es importante que cree ensamblados de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="56305-118">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="56305-119">En este escenario, debe crear un archivo independiente de los módulos de código que solo contenga el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="56305-119">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="56305-120">Internet Explorer descarga primero el manifiesto del ensamblado y, después, crea subprocesos de trabajo para descargar los módulos o ensamblados adicionales necesarios.</span><span class="sxs-lookup"><span data-stu-id="56305-120">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="56305-121">Mientras se descarga el archivo que contiene el manifiesto del ensamblado, Internet Explorer no responde a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="56305-121">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="56305-122">Cuanto menor sea el archivo que contiene el manifiesto del ensamblado, menos tiempo estará sin responder Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="56305-122">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="56305-123">Para combinar módulos de código escritos por varios desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="56305-123">To combine code modules written by several developers.</span></span> <span data-ttu-id="56305-124">Aunque cada desarrollador puede compilar cada módulo de código en un ensamblado, esto puede hacer que se expongan públicamente algunos tipos que no se exponen cuando todos los módulos se colocan en un ensamblado de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="56305-124">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="56305-125">Una vez creado el ensamblado, puede firmar el archivo que contiene el manifiesto del ensamblado (y, por tanto, el ensamblado), o bien puede asignarle al archivo y al ensamblado un nombre seguro y colocarlo en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="56305-125">Once you create the assembly, you can sign the file that contains the assembly manifest, and hence the assembly, or you can give the file and the assembly a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="56305-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="56305-126">See also</span></span>

- [<span data-ttu-id="56305-127">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="56305-127">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="56305-128">Programación con ensamblados</span><span class="sxs-lookup"><span data-stu-id="56305-128">Program with assemblies</span></span>](../../standard/assembly/index.md)
