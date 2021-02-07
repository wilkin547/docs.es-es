---
description: 'Más información sobre: clase UnsafeNclNativeMethods'
title: Clase UnsafeNclNativeMethods (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fa1084efddae0ba5cbfc9a949dcd94d2c64f3272
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699498"
---
# <a name="unsafenclnativemethods-class"></a><span data-ttu-id="bde5d-103">Clase UnsafeNclNativeMethods</span><span class="sxs-lookup"><span data-stu-id="bde5d-103">UnsafeNclNativeMethods class</span></span>

<span data-ttu-id="bde5d-104">Contiene clases que importan métodos de red nativos no seguros.</span><span class="sxs-lookup"><span data-stu-id="bde5d-104">Contains classes that import unsafe native networking methods.</span></span> <span data-ttu-id="bde5d-105">Esta clase no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="bde5d-105">This class cannot be inherited.</span></span>

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> <span data-ttu-id="bde5d-106">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="bde5d-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bde5d-107">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="bde5d-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="nativepki-class"></a><span data-ttu-id="bde5d-108">Clase NativePKI</span><span class="sxs-lookup"><span data-stu-id="bde5d-108">NativePKI class</span></span>

<span data-ttu-id="bde5d-109">Contiene métodos importados desde crypt32.dll.</span><span class="sxs-lookup"><span data-stu-id="bde5d-109">Contains methods imported from crypt32.dll.</span></span> <span data-ttu-id="bde5d-110">Estos métodos controlan los certificados cuando se usa el protocolo de transferencia de hipertexto seguro (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="bde5d-110">These methods handle certificates when using Hypertext Transfer Protocol Secure (HTTPS).</span></span> <span data-ttu-id="bde5d-111">Esta clase no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="bde5d-111">This class cannot be inherited.</span></span>

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a><span data-ttu-id="bde5d-112">NativePKI. FindClientCertificates, método</span><span class="sxs-lookup"><span data-stu-id="bde5d-112">NativePKI.FindClientCertificates method</span></span>

<span data-ttu-id="bde5d-113">Detecta los certificados de cliente disponibles para enviar al servidor.</span><span class="sxs-lookup"><span data-stu-id="bde5d-113">Discovers available client certificates to send to the server.</span></span>

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a><span data-ttu-id="bde5d-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bde5d-114">Return value</span></span>

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

<span data-ttu-id="bde5d-115">Colección de certificados de cliente disponibles.</span><span class="sxs-lookup"><span data-stu-id="bde5d-115">A collection of available client certificates.</span></span>

## <a name="requirements"></a><span data-ttu-id="bde5d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bde5d-116">Requirements</span></span>

<span data-ttu-id="bde5d-117">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="bde5d-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="bde5d-118">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="bde5d-118">**Assembly:** System (in System.dll)</span></span>
