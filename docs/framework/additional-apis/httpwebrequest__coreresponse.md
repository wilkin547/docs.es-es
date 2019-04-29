---
title: Campo HttpWebRequest._CoreResponse
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706070"
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="1b1ab-102">HttpWebRequest. \_CoreResponse campo</span><span class="sxs-lookup"><span data-stu-id="1b1ab-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="1b1ab-103">`HttpWebRequest._CoreResponse` es un objeto (ya sea un [CoreResponseData](coreresponsedata.md) o <xref:System.Exception>) que contiene el resultado del análisis de respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="1b1ab-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b1ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b1ab-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="1b1ab-105">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="1b1ab-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="1b1ab-106">En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="1b1ab-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="1b1ab-107">Consulte [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="1b1ab-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="1b1ab-108">Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="1b1ab-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b1ab-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b1ab-109">Requirements</span></span>

<span data-ttu-id="1b1ab-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="1b1ab-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="1b1ab-111">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="1b1ab-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="1b1ab-112">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="1b1ab-112">**.NET Framework versions:** Available since 2.0.</span></span>
