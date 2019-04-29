---
title: Campo CoreResponseData.m_ResponseHeaders
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
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705979"
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="01c21-102">CoreResponseData.m\_ResponseHeaders campo</span><span class="sxs-lookup"><span data-stu-id="01c21-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="01c21-103">`CoreResponseData.m_ResponseHeaders` es un <xref:System.Net.WebHeaderCollection> de encabezados asociados con la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="01c21-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="01c21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01c21-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="01c21-105">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="01c21-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="01c21-106">En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="01c21-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="01c21-107">Consulte [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="01c21-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="01c21-108">Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="01c21-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="01c21-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01c21-109">Requirements</span></span>

<span data-ttu-id="01c21-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="01c21-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="01c21-111">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="01c21-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="01c21-112">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="01c21-112">**.NET Framework versions:** Available since 2.0.</span></span>
