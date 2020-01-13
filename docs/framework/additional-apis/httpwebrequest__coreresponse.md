---
title: Campo HttpWebRequest. _CoreResponse
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
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740452"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="f2c23-102">HttpWebRequest.\_campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="f2c23-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="f2c23-103">`HttpWebRequest._CoreResponse` es un objeto ( [CoreResponseData](coreresponsedata.md) o un <xref:System.Exception>) que contiene el resultado del análisis de respuesta http.</span><span class="sxs-lookup"><span data-stu-id="f2c23-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2c23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2c23-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="f2c23-105">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="f2c23-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="f2c23-106">En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="f2c23-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="f2c23-107">Consulte [la guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="f2c23-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="f2c23-108">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="f2c23-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f2c23-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f2c23-109">Requirements</span></span>

<span data-ttu-id="f2c23-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f2c23-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f2c23-111">**Ensamblado:** Sistema (en System. dll)</span><span class="sxs-lookup"><span data-stu-id="f2c23-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f2c23-112">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="f2c23-112">**.NET Framework versions:** Available since 2.0.</span></span>
