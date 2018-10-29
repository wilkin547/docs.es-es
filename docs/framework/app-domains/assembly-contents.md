---
title: Contenido de los ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aed7e1e9e85f746c4b55b10c59dd82e85565b00
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194844"
---
# <a name="assembly-contents"></a><span data-ttu-id="a3b89-102">Contenido de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="a3b89-102">Assembly Contents</span></span>
<span data-ttu-id="a3b89-103">En general, un ensamblado estático está formado por cuatro elementos:</span><span class="sxs-lookup"><span data-stu-id="a3b89-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="a3b89-104">El [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md), que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a3b89-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="a3b89-105">Los metadatos de tipos.</span><span class="sxs-lookup"><span data-stu-id="a3b89-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="a3b89-106">El código de lenguaje intermedio de Microsoft (MSIL) que implementa los tipos.</span><span class="sxs-lookup"><span data-stu-id="a3b89-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="a3b89-107">Un conjunto de recursos.</span><span class="sxs-lookup"><span data-stu-id="a3b89-107">A set of resources.</span></span>  
  
 <span data-ttu-id="a3b89-108">El manifiesto del ensamblado es el único elemento obligatorio, pero se necesitan o bien los tipos o bien los recursos para proporcionar al ensamblado una funcionalidad significativa.</span><span class="sxs-lookup"><span data-stu-id="a3b89-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="a3b89-109">Estos elementos se pueden agrupar en un ensamblado de varias formas.</span><span class="sxs-lookup"><span data-stu-id="a3b89-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="a3b89-110">Se puede agrupar todos los elementos en un solo archivo físico, como se observa en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3b89-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="a3b89-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="a3b89-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="a3b89-112">Ensamblado de único archivo</span><span class="sxs-lookup"><span data-stu-id="a3b89-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="a3b89-113">Alternativamente, los elementos de un ensamblado se pueden incluir en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="a3b89-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="a3b89-114">Estos archivos pueden ser módulos de código compilado (.netmodule), de recursos (como archivos .bmp o .jpg) u otros archivos necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3b89-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="a3b89-115">Puede crear un ensamblado de múltiples archivos para combinar módulos escritos en idiomas diferentes y optimizar la descarga de una aplicación al colocar los tipos que rara vez se utilizan en un módulo que se descargue sólo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3b89-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="a3b89-116">En la siguiente ilustración, el programador de una aplicación hipotética ha decidido separar el código de alguna utilidad en un módulo diferente y mantener un archivo de recursos grande (en este caso, una imagen .bmp) en su archivo original.</span><span class="sxs-lookup"><span data-stu-id="a3b89-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="a3b89-117">.NET Framework descarga un archivo sólo cuando se hace referencia al mismo, por lo que la descarga de código se ve optimizada cuando se mantiene el código al que no se hace referencia frecuentemente en un archivo aparte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3b89-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="a3b89-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="a3b89-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="a3b89-119">Ensamblado de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="a3b89-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3b89-120">El sistema de archivos no vincula físicamente los archivos que forman un ensamblado de múltiples archivos.</span><span class="sxs-lookup"><span data-stu-id="a3b89-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="a3b89-121">En su lugar, se vinculan a través del manifiesto del ensamblado y Common Language Runtime los administra como una unidad.</span><span class="sxs-lookup"><span data-stu-id="a3b89-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="a3b89-122">En esta ilustración, los tres archivos pertenecen a un ensamblado, como se describe en el manifiesto del ensamblado contenido en MyAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="a3b89-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="a3b89-123">Para el sistema de archivos, se trata de tres archivos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a3b89-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="a3b89-124">Tenga en cuenta que el archivo Util.netmodule se compiló como módulo porque no contiene información de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a3b89-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="a3b89-125">Cuando se creó el ensamblado, el manifiesto del ensamblado se agregó a MyAssembly.dll, lo que indica su relación con Util.netmodule y Graphic.bmp.</span><span class="sxs-lookup"><span data-stu-id="a3b89-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="a3b89-126">Actualmente, al diseñar el código fuente, se toman decisiones explícitas sobre cómo repartir la funcionalidad de una aplicación entre uno o más archivos.</span><span class="sxs-lookup"><span data-stu-id="a3b89-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="a3b89-127">Al diseñar el código de .NET Framework, tomará decisiones similares sobre cómo dividir la funcionalidad en uno o más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a3b89-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b89-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b89-128">See Also</span></span>  
- [<span data-ttu-id="a3b89-129">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a3b89-129">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
- [<span data-ttu-id="a3b89-130">Manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="a3b89-130">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)  
- [<span data-ttu-id="a3b89-131">Consideraciones de seguridad sobre ensamblados</span><span class="sxs-lookup"><span data-stu-id="a3b89-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
