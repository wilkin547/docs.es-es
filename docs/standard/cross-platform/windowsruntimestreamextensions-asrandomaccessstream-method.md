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
ms.openlocfilehash: a712414163446606cbc93154bc821d3b1166fe8f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561801"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="69ff6-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)</span><span class="sxs-lookup"><span data-stu-id="69ff6-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>

<span data-ttu-id="69ff6-103">[Compatible con .NET Framework 4.5.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="69ff6-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>

<span data-ttu-id="69ff6-104">Convierte la secuencia especificada en una secuencia de acceso aleatorio.</span><span class="sxs-lookup"><span data-stu-id="69ff6-104">Converts the specified stream to a random access stream.</span></span>

<span data-ttu-id="69ff6-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType> 
 **ensamblado:** System.Runtime.WindowsRuntime (en System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="69ff6-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>

## <a name="syntax"></a><span data-ttu-id="69ff6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69ff6-106">Syntax</span></span>

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a><span data-ttu-id="69ff6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69ff6-107">Parameters</span></span>

`stream`

<span data-ttu-id="69ff6-108">Tipo: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="69ff6-108">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="69ff6-109">La secuencia que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="69ff6-109">The stream to convert.</span></span>

## <a name="return-value"></a><span data-ttu-id="69ff6-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69ff6-110">Return Value</span></span>

<span data-ttu-id="69ff6-111">Tipo: <xref:Windows.Storage.Streams.RandomAccessStream></span><span class="sxs-lookup"><span data-stu-id="69ff6-111">Type: <xref:Windows.Storage.Streams.RandomAccessStream></span></span>  
<span data-ttu-id="69ff6-112">Un [!INCLUDE[wrt](../../../includes/wrt-md.md)] secuencia de acceso aleatorio, que representa la secuencia convertida.</span><span class="sxs-lookup"><span data-stu-id="69ff6-112">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>

## <a name="exceptions"></a><span data-ttu-id="69ff6-113">Excepciones</span><span class="sxs-lookup"><span data-stu-id="69ff6-113">Exceptions</span></span>

|<span data-ttu-id="69ff6-114">Excepción</span><span class="sxs-lookup"><span data-stu-id="69ff6-114">Exception</span></span>|<span data-ttu-id="69ff6-115">Condición</span><span class="sxs-lookup"><span data-stu-id="69ff6-115">Condition</span></span>|
|---------------|---------------|
|<xref:System.NotSupportedException>|<span data-ttu-id="69ff6-116">La secuencia que se va a convertir no admite operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="69ff6-116">The stream to convert does not support seeking.</span></span>|

## <a name="remarks"></a><span data-ttu-id="69ff6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69ff6-117">Remarks</span></span>

<span data-ttu-id="69ff6-118">Este método de extensión solo está disponible al desarrollar aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="69ff6-118">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="69ff6-119">Este método proporciona una forma cómoda de trabajar con secuencias en las aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="69ff6-119">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="69ff6-120">La secuencia de .NET Framework que desea convertir debe admitir operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="69ff6-120">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="69ff6-121">Para obtener más información, vea el método <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69ff6-121">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69ff6-122">Esta API es compatible con .NET Framework 4.5.1 y versiones posteriores, pero no con la versión 4.5.</span><span class="sxs-lookup"><span data-stu-id="69ff6-122">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>

## <a name="version-information"></a><span data-ttu-id="69ff6-123">Información de versión</span><span class="sxs-lookup"><span data-stu-id="69ff6-123">Version Information</span></span>

<span data-ttu-id="69ff6-124">**.NET para aplicaciones de Windows Store**</span><span class="sxs-lookup"><span data-stu-id="69ff6-124">**.NET for Windows Store apps**</span></span>

<span data-ttu-id="69ff6-125">Se admite en: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="69ff6-125">Supported in: Windows 8.1</span></span>

## <a name="see-also"></a><span data-ttu-id="69ff6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="69ff6-126">See Also</span></span>

<span data-ttu-id="69ff6-127">[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)</span><span class="sxs-lookup"><span data-stu-id="69ff6-127">[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)</span></span>  
[<span data-ttu-id="69ff6-128">Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa</span><span class="sxs-lookup"><span data-stu-id="69ff6-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  