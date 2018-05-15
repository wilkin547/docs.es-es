---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16f878abc11589fe62f78d941b367d82d7b49e1c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="c41b1-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)</span><span class="sxs-lookup"><span data-stu-id="c41b1-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="c41b1-103">[Compatible con .NET Framework 4.5.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="c41b1-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="c41b1-104">Convierte la secuencia especificada en una secuencia de acceso aleatorio.</span><span class="sxs-lookup"><span data-stu-id="c41b1-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="c41b1-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c41b1-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="c41b1-106">**Ensamblado:** System.Runtime.WindowsRuntime (de System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="c41b1-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c41b1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c41b1-107">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="c41b1-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c41b1-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="c41b1-109">Tipo: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c41b1-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="c41b1-110">La secuencia que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="c41b1-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c41b1-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c41b1-111">Return Value</span></span>  
 <span data-ttu-id="c41b1-112">Tipo: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="c41b1-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="c41b1-113">Un [!INCLUDE[wrt](../../../includes/wrt-md.md)] secuencia de acceso aleatorio, que representa la secuencia convertida.</span><span class="sxs-lookup"><span data-stu-id="c41b1-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="c41b1-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="c41b1-114">Exceptions</span></span>  
  
|<span data-ttu-id="c41b1-115">Excepción</span><span class="sxs-lookup"><span data-stu-id="c41b1-115">Exception</span></span>|<span data-ttu-id="c41b1-116">Condición</span><span class="sxs-lookup"><span data-stu-id="c41b1-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="c41b1-117">La secuencia que se va a convertir no admite operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c41b1-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c41b1-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c41b1-118">Remarks</span></span>  
 <span data-ttu-id="c41b1-119">Este método de extensión solo está disponible al desarrollar aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="c41b1-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="c41b1-120">Este método proporciona una forma cómoda de trabajar con secuencias en las aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="c41b1-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="c41b1-121">La secuencia de .NET Framework que desea convertir debe admitir operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c41b1-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="c41b1-122">Para obtener más información, vea el método <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c41b1-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c41b1-123">Esta API es compatible con .NET Framework 4.5.1 y versiones posteriores, pero no con la versión 4.5.</span><span class="sxs-lookup"><span data-stu-id="c41b1-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="c41b1-124">Información de versión</span><span class="sxs-lookup"><span data-stu-id="c41b1-124">Version Information</span></span>  
 <span data-ttu-id="c41b1-125">**.NET para aplicaciones de la tienda de Windows**</span><span class="sxs-lookup"><span data-stu-id="c41b1-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="c41b1-126">Se admite en: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c41b1-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41b1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c41b1-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="c41b1-128">Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa</span><span class="sxs-lookup"><span data-stu-id="c41b1-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
