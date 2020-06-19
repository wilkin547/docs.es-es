---
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
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990495"
---
# <a name="unsafenclnativemethods-class"></a><span data-ttu-id="27cd7-102">Clase UnsafeNclNativeMethods</span><span class="sxs-lookup"><span data-stu-id="27cd7-102">UnsafeNclNativeMethods class</span></span>

<span data-ttu-id="27cd7-103">Contiene clases que importan métodos de red nativos no seguros.</span><span class="sxs-lookup"><span data-stu-id="27cd7-103">Contains classes that import unsafe native networking methods.</span></span> <span data-ttu-id="27cd7-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="27cd7-104">This class cannot be inherited.</span></span>

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> <span data-ttu-id="27cd7-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="27cd7-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="27cd7-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="27cd7-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="nativepki-class"></a><span data-ttu-id="27cd7-107">Clase NativePKI</span><span class="sxs-lookup"><span data-stu-id="27cd7-107">NativePKI class</span></span>

<span data-ttu-id="27cd7-108">Contiene métodos importados desde crypt32.dll.</span><span class="sxs-lookup"><span data-stu-id="27cd7-108">Contains methods imported from crypt32.dll.</span></span> <span data-ttu-id="27cd7-109">Estos métodos controlan los certificados cuando se usa el protocolo de transferencia de hipertexto seguro (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="27cd7-109">These methods handle certificates when using Hypertext Transfer Protocol Secure (HTTPS).</span></span> <span data-ttu-id="27cd7-110">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="27cd7-110">This class cannot be inherited.</span></span>

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a><span data-ttu-id="27cd7-111">NativePKI. FindClientCertificates, método</span><span class="sxs-lookup"><span data-stu-id="27cd7-111">NativePKI.FindClientCertificates method</span></span>

<span data-ttu-id="27cd7-112">Detecta los certificados de cliente disponibles para enviar al servidor.</span><span class="sxs-lookup"><span data-stu-id="27cd7-112">Discovers available client certificates to send to the server.</span></span>

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a><span data-ttu-id="27cd7-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27cd7-113">Return value</span></span>

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

<span data-ttu-id="27cd7-114">Colección de certificados de cliente disponibles.</span><span class="sxs-lookup"><span data-stu-id="27cd7-114">A collection of available client certificates.</span></span>

## <a name="requirements"></a><span data-ttu-id="27cd7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27cd7-115">Requirements</span></span>

<span data-ttu-id="27cd7-116">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="27cd7-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="27cd7-117">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="27cd7-117">**Assembly:** System (in System.dll)</span></span>
