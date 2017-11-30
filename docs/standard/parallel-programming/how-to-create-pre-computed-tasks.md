---
title: "Cómo: Crear tareas precalculadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4596b28afe48aad4a84a7dd72b4a1d44a9ada8a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="9f8d6-102">Cómo: Crear tareas precalculadas</span><span class="sxs-lookup"><span data-stu-id="9f8d6-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="9f8d6-103">Este documento describe cómo utilizar el <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> método para recuperar los resultados de las operaciones de descarga asincrónica que se mantienen en una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="9f8d6-104">El <xref:System.Threading.Tasks.Task.FromResult%2A> método devuelve un terminado <xref:System.Threading.Tasks.Task%601> objeto que contiene el valor proporcionado como su <xref:System.Threading.Tasks.Task%601.Result%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="9f8d6-105">Este método es útil cuando se realiza una operación asincrónica que devuelve un objeto <xref:System.Threading.Tasks.Task%601> y el resultado de ese objeto <xref:System.Threading.Tasks.Task%601> ya se ha calculado.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f8d6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f8d6-106">Example</span></span>  
 <span data-ttu-id="9f8d6-107">En el ejemplo siguiente se descarga cadenas desde la web.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="9f8d6-108">Define la `DownloadStringAsync` método.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="9f8d6-109">Este método descargas de cadenas de forma asincrónica desde la web.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="9f8d6-110">Este ejemplo también utiliza un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto que se va a almacenar en caché los resultados de las operaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="9f8d6-111">Si la dirección de entrada se mantiene en esta memoria caché, `DownloadStringAsync` utiliza la <xref:System.Threading.Tasks.Task.FromResult%2A> método para generar un <xref:System.Threading.Tasks.Task%601> objeto que contiene el contenido en esa dirección.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="9f8d6-112">En caso contrario, `DownloadStringAsync` descarga el archivo desde la web y agrega el resultado a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="9f8d6-113">Este ejemplo calcula el tiempo necesario para descargar varias cadenas dos veces.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="9f8d6-114">El segundo conjunto de operaciones de descarga tardará menos tiempo que el primer conjunto porque los resultados se mantienen en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="9f8d6-115">El <xref:System.Threading.Tasks.Task.FromResult%2A> método habilita el `DownloadStringAsync` método para crear <xref:System.Threading.Tasks.Task%601> objetos que contienen estos precalculadas resultados.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f8d6-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9f8d6-116">Compiling the Code</span></span>  
 <span data-ttu-id="9f8d6-117">Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `CachedDownloads.cs` (`CachedDownloads.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="9f8d6-118">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="9f8d6-118">**csc.exe CachedDownloads.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="9f8d6-119">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="9f8d6-119">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9f8d6-120">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9f8d6-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8d6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f8d6-121">See Also</span></span>  
 [<span data-ttu-id="9f8d6-122">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="9f8d6-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
