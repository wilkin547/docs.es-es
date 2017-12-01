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
# <a name="how-to-create-pre-computed-tasks"></a>Cómo: Crear tareas precalculadas
Este documento describe cómo utilizar el <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> método para recuperar los resultados de las operaciones de descarga asincrónica que se mantienen en una memoria caché. El <xref:System.Threading.Tasks.Task.FromResult%2A> método devuelve un terminado <xref:System.Threading.Tasks.Task%601> objeto que contiene el valor proporcionado como su <xref:System.Threading.Tasks.Task%601.Result%2A> propiedad. Este método es útil cuando se realiza una operación asincrónica que devuelve un objeto <xref:System.Threading.Tasks.Task%601> y el resultado de ese objeto <xref:System.Threading.Tasks.Task%601> ya se ha calculado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se descarga cadenas desde la web. Define la `DownloadStringAsync` método. Este método descargas de cadenas de forma asincrónica desde la web. Este ejemplo también utiliza un <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objeto que se va a almacenar en caché los resultados de las operaciones anteriores. Si la dirección de entrada se mantiene en esta memoria caché, `DownloadStringAsync` utiliza la <xref:System.Threading.Tasks.Task.FromResult%2A> método para generar un <xref:System.Threading.Tasks.Task%601> objeto que contiene el contenido en esa dirección. En caso contrario, `DownloadStringAsync` descarga el archivo desde la web y agrega el resultado a la memoria caché.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 Este ejemplo calcula el tiempo necesario para descargar varias cadenas dos veces. El segundo conjunto de operaciones de descarga tardará menos tiempo que el primer conjunto porque los resultados se mantienen en la memoria caché. El <xref:System.Threading.Tasks.Task.FromResult%2A> método habilita el `DownloadStringAsync` método para crear <xref:System.Threading.Tasks.Task%601> objetos que contienen estos precalculadas resultados.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `CachedDownloads.cs` (`CachedDownloads.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe CachedDownloads.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe CachedDownloads.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
