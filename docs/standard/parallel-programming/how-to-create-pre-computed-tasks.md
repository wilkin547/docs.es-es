---
title: 'Cómo: Crear tareas precalculadas'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47e4c5d721b37388a4008d100f5212057477c638
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44211663"
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="1f982-102">Cómo: Crear tareas precalculadas</span><span class="sxs-lookup"><span data-stu-id="1f982-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="1f982-103">En este documento se describe cómo utilizar el método <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> para recuperar los resultados de las operaciones asincrónicas de descarga que se retienen en una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1f982-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="1f982-104">El método <xref:System.Threading.Tasks.Task.FromResult%2A> devuelve un objeto <xref:System.Threading.Tasks.Task%601> terminado que contiene el valor proporcionado como su propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f982-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="1f982-105">Este método es útil cuando se realiza una operación asincrónica que devuelve un objeto <xref:System.Threading.Tasks.Task%601> y el resultado de ese objeto <xref:System.Threading.Tasks.Task%601> ya se ha calculado.</span><span class="sxs-lookup"><span data-stu-id="1f982-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f982-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f982-106">Example</span></span>  
 <span data-ttu-id="1f982-107">En el ejemplo siguiente se descargan cadenas desde la Web.</span><span class="sxs-lookup"><span data-stu-id="1f982-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="1f982-108">Define el método `DownloadStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="1f982-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="1f982-109">Este método descarga cadenas de la Web de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="1f982-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="1f982-110">En este ejemplo también se usa un objeto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> para almacenar en caché los resultados de las operaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="1f982-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="1f982-111">Si la dirección de entrada se mantiene en esta memoria caché, `DownloadStringAsync` utiliza el método <xref:System.Threading.Tasks.Task.FromResult%2A> para generar un objeto <xref:System.Threading.Tasks.Task%601> que incluye el contenido en esa dirección.</span><span class="sxs-lookup"><span data-stu-id="1f982-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="1f982-112">En caso contrario, `DownloadStringAsync` descarga el archivo desde la Web y agrega el resultado a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1f982-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="1f982-113">Este ejemplo calcula el tiempo necesario para descargar varias cadenas dos veces.</span><span class="sxs-lookup"><span data-stu-id="1f982-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="1f982-114">El segundo conjunto de operaciones de descarga debe tardar menos tiempo que el primer conjunto porque los resultados se mantienen en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1f982-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="1f982-115">El método <xref:System.Threading.Tasks.Task.FromResult%2A> habilita el método `DownloadStringAsync` para crear objetos <xref:System.Threading.Tasks.Task%601> que contienen estos resultados precalculados.</span><span class="sxs-lookup"><span data-stu-id="1f982-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1f982-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1f982-116">Compiling the Code</span></span>  
 <span data-ttu-id="1f982-117">Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `CachedDownloads.cs` (`CachedDownloads.vb` para Visual Basic) y, luego, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f982-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="1f982-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="1f982-118">Visual C#</span></span>  
  
 <span data-ttu-id="1f982-119">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="1f982-119">**csc.exe CachedDownloads.cs**</span></span>  
  
 <span data-ttu-id="1f982-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f982-120">Visual Basic</span></span>  
  
 <span data-ttu-id="1f982-121">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="1f982-121">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1f982-122">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1f982-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f982-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f982-123">See also</span></span>

- [<span data-ttu-id="1f982-124">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="1f982-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
