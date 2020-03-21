---
title: CoreResponseData.m_ResponseHeaders Field
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 723df6dc2de978695608d106e3a01bde286fc4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156108"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="30f98-102">Campo CoreResponseData.m\_ResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="30f98-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="30f98-103">`CoreResponseData.m_ResponseHeaders`es <xref:System.Net.WebHeaderCollection> un de los encabezados asociados con la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="30f98-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="30f98-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30f98-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="30f98-105">Esta API no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="30f98-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="30f98-106">En su lugar, <xref:System.Diagnostics.DiagnosticSource> debe usar a para enlazar código de red.</span><span class="sxs-lookup"><span data-stu-id="30f98-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="30f98-107">Consulte [Guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="30f98-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="30f98-108">Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="30f98-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="30f98-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30f98-109">Requirements</span></span>

<span data-ttu-id="30f98-110">**Espacio de nombres:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="30f98-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="30f98-111">**Montaje:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="30f98-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="30f98-112">**Versiones de .NET Framework:** Disponible desde 2.0.</span><span class="sxs-lookup"><span data-stu-id="30f98-112">**.NET Framework versions:** Available since 2.0.</span></span>
