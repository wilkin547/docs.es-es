---
title: Ensamblados de varios archivos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7851375c03f9caacd9c89d33e5a03212581d7937
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="multifile-assemblies"></a><span data-ttu-id="ef2ee-102">Ensamblados de varios archivos</span><span class="sxs-lookup"><span data-stu-id="ef2ee-102">Multifile Assemblies</span></span>
<span data-ttu-id="ef2ee-103">Puede crear ensamblados de varios archivos mediante compiladores de línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-103">You can create multifile assemblies using command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] with Visual C++.</span></span> <span data-ttu-id="ef2ee-104">Un archivo del ensamblado debe contener el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-104">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="ef2ee-105">Los ensamblados que inicien una aplicación también deben contener un punto de entrada, como un método Main o WinMain.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-105">An assembly that starts an application must also contain an entry point, such as a Main or WinMain method.</span></span>  
  
 <span data-ttu-id="ef2ee-106">Por ejemplo, supongamos que tiene una aplicación que contiene dos módulos de código, Client.cs y Stringer.cs.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-106">For example, suppose you have an application that contains two code modules, Client.cs and Stringer.cs.</span></span> <span data-ttu-id="ef2ee-107">Stringer.cs que crea el espacio de nombres `myStringer` al que hace referencia el código de Client.cs.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-107">Stringer.cs creates the `myStringer` namespace that is referenced by the code in Client.cs.</span></span> <span data-ttu-id="ef2ee-108">Client.cs contiene el método `Main`, que es el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-108">Client.cs contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="ef2ee-109">En este ejemplo, se compilan los dos módulos de código y, después, se crea un tercer archivo que contiene el manifiesto del ensamblado, que inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-109">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="ef2ee-110">El manifiesto del ensamblado hace referencia a los módulos `Client` y `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-110">The assembly manifest references both the `Client` and `Stringer` modules.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef2ee-111">Los ensamblados de varios archivos pueden tener un único punto de entrada, incluso si el ensamblado tiene varios módulos de código.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-111">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>  
  
 <span data-ttu-id="ef2ee-112">Hay varias razones por las que le puede interesar crear un ensamblado de varios archivos:</span><span class="sxs-lookup"><span data-stu-id="ef2ee-112">There are several reasons you might want to create a multifile assembly:</span></span>  
  
-   <span data-ttu-id="ef2ee-113">Para combinar módulos escritos en lenguajes diferentes.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-113">To combine modules written in different languages.</span></span> <span data-ttu-id="ef2ee-114">Esta es la razón más común para crear un ensamblado de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-114">This is the most common reason for creating a multifile assembly.</span></span>  
  
-   <span data-ttu-id="ef2ee-115">Para optimizar la descarga de una aplicación al colocar los tipos menos usados en un módulo que solo se descarga cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-115">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef2ee-116">Si va a crear aplicaciones que se descargarán mediante la etiqueta `<object>` con Microsoft Internet Explorer, es importante que cree ensamblados de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-116">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="ef2ee-117">En este escenario, debe crear un archivo independiente de los módulos de código que solo contenga el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-117">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="ef2ee-118">Internet Explorer descarga primero el manifiesto del ensamblado y, después, crea subprocesos de trabajo para descargar los módulos o ensamblados adicionales necesarios.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-118">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="ef2ee-119">Mientras se descarga el archivo que contiene el manifiesto del ensamblado, Internet Explorer no responde a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-119">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="ef2ee-120">Cuanto menor sea el archivo que contiene el manifiesto del ensamblado, menos tiempo estará sin responder Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-120">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>  
  
-   <span data-ttu-id="ef2ee-121">Para combinar módulos de código escritos por varios desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-121">To combine code modules written by several developers.</span></span> <span data-ttu-id="ef2ee-122">Aunque cada desarrollador puede compilar cada módulo de código en un ensamblado, esto puede hacer que se expongan públicamente algunos tipos que no se exponen cuando todos los módulos se colocan en un ensamblado de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-122">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>  
  
 <span data-ttu-id="ef2ee-123">Una vez creado el ensamblado, puede firmar el archivo que contiene el manifiesto del ensamblado (y, por tanto, el ensamblado), o bien puede asignarle al archivo (y al ensamblado) un nombre seguro y colocarlo en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ef2ee-123">Once you create the assembly, you can sign the file that contains the assembly manifest (and hence the assembly), or you can give the file (and the assembly) a strong name and put it in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2ee-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef2ee-124">See Also</span></span>  
 <span data-ttu-id="ef2ee-125">[Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="ef2ee-125">[How to: Build a Multifile Assembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span></span>  
 [<span data-ttu-id="ef2ee-126">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="ef2ee-126">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

