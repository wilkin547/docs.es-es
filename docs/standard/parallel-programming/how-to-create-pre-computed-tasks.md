---
title: "How to: Create Pre-Computed Tasks | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, creating pre-computed"
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Create Pre-Computed Tasks
Este documento se describe cómo usar el método de <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=fullName> para recuperar los resultados de las operaciones asincrónicas de descarga que se retienen en la memoria caché.  El método de <xref:System.Threading.Tasks.Task.FromResult%2A> devuelve un objeto terminado de <xref:System.Threading.Tasks.Task%601> que celebre el valor proporcionado como su propiedad de <xref:System.Threading.Tasks.Task%601.Result%2A> .  Este método es útil cuando se realiza una operación asincrónica que devuelve un objeto <xref:System.Threading.Tasks.Task%601> y el resultado de ese objeto <xref:System.Threading.Tasks.Task%601> ya se ha calculado.  
  
## Ejemplo  
 El ejemplo siguiente descarga las cadenas de web.  Define el método de `DownloadStringAsync` .  Este método descarga las cadenas de web de forma asincrónica.  Este ejemplo también utiliza un objeto de <xref:System.Collections.Concurrent.ConcurrentDictionary%602> almacenar en caché los resultados de operaciones anteriores.  Si se celebra la dirección de la entrada en esta memoria caché, `DownloadStringAsync` utiliza el método de <xref:System.Threading.Tasks.Task.FromResult%2A> para generar un objeto de <xref:System.Threading.Tasks.Task%601> que contiene el contenido en esa dirección.  Si no, `DownloadStringAsync` descarga el archivo web y agrega el resultado a la memoria caché.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 Este ejemplo calcula el tiempo necesario para descargar varias cadenas dos veces.  El segundo conjunto de operaciones de descarga debe tardar menos tiempo que el primer conjunto porque los resultados se retienen en la memoria caché.  El método de <xref:System.Threading.Tasks.Task.FromResult%2A> permite que el método de `DownloadStringAsync` para crear los objetos de <xref:System.Threading.Tasks.Task%601> que contienen estos resultados pre\- calculados.  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `CachedDownloads.cs` \(`CachedDownloads.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe CachedDownloads.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe CachedDownloads.vb**  
  
## Programación eficaz  
  
## Vea también  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)