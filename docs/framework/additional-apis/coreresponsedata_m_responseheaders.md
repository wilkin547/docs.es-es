---
title: Campo CoreResponseData. m_ResponseHeaders
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
ms.openlocfilehash: df0b592a5f85d4c99dee4ecb60963f4abb560a13
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741012"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="6929a-102">CoreResponseData. m\_campo ResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="6929a-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="6929a-103">`CoreResponseData.m_ResponseHeaders` es una <xref:System.Net.WebHeaderCollection> de encabezados asociada a la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="6929a-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="6929a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6929a-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="6929a-105">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="6929a-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="6929a-106">En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="6929a-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="6929a-107">Consulte [la guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="6929a-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="6929a-108">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="6929a-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6929a-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6929a-109">Requirements</span></span>

<span data-ttu-id="6929a-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6929a-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6929a-111">**Ensamblado:** Sistema (en System. dll)</span><span class="sxs-lookup"><span data-stu-id="6929a-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="6929a-112">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="6929a-112">**.NET Framework versions:** Available since 2.0.</span></span>
