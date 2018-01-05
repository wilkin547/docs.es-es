---
title: "WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)"
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
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9057eabb7e3dfdfaa872fbcf2fe1180d0bbc7920
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="78880-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)</span><span class="sxs-lookup"><span data-stu-id="78880-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="78880-103">[Compatible con .NET Framework 4.5.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="78880-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="78880-104">Convierte la secuencia especificada en una secuencia de acceso aleatorio.</span><span class="sxs-lookup"><span data-stu-id="78880-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="78880-105">**Namespace:**<xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="78880-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="78880-106">**Ensamblado:** System.Runtime.WindowsRuntime (de System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="78880-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78880-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78880-107">Syntax</span></span>  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78880-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78880-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="78880-109">Tipo: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="78880-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="78880-110">La secuencia que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="78880-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78880-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78880-111">Return Value</span></span>  
 <span data-ttu-id="78880-112">Tipo: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="78880-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="78880-113">Un [!INCLUDE[wrt](../../../includes/wrt-md.md)] secuencia de acceso aleatorio, que representa la secuencia convertida.</span><span class="sxs-lookup"><span data-stu-id="78880-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="78880-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="78880-114">Exceptions</span></span>  
  
|<span data-ttu-id="78880-115">Excepción</span><span class="sxs-lookup"><span data-stu-id="78880-115">Exception</span></span>|<span data-ttu-id="78880-116">Condición</span><span class="sxs-lookup"><span data-stu-id="78880-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="78880-117">La secuencia que se va a convertir no admite operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78880-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78880-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78880-118">Remarks</span></span>  
 <span data-ttu-id="78880-119">Este método de extensión solo está disponible al desarrollar aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="78880-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="78880-120">Este método proporciona una forma cómoda de trabajar con secuencias en las aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="78880-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="78880-121">La secuencia de .NET Framework que desea convertir debe admitir operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78880-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="78880-122">Para obtener más información, vea el método <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78880-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="78880-123">Esta API es compatible con .NET Framework 4.5.1 y versiones posteriores, pero no con la versión 4.5.</span><span class="sxs-lookup"><span data-stu-id="78880-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="78880-124">Información de versión</span><span class="sxs-lookup"><span data-stu-id="78880-124">Version Information</span></span>  
 <span data-ttu-id="78880-125">**.NET para aplicaciones de la tienda de Windows**</span><span class="sxs-lookup"><span data-stu-id="78880-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="78880-126">Se admite en: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="78880-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78880-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="78880-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="78880-128">Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa</span><span class="sxs-lookup"><span data-stu-id="78880-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
