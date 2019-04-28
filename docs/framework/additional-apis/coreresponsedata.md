---
title: Clase CoreResponseData
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675421"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="99dd5-102">Clase CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="99dd5-102">CoreResponseData Class</span></span>

<span data-ttu-id="99dd5-103">La `CoreResponseData` clase representa el análisis de los encabezados HTTP y el cuerpo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="99dd5-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="99dd5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99dd5-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="99dd5-105">Esta API es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="99dd5-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="99dd5-106">En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="99dd5-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="99dd5-107">Consulte [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="99dd5-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="99dd5-108">Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="99dd5-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="99dd5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99dd5-109">Requirements</span></span>

<span data-ttu-id="99dd5-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="99dd5-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="99dd5-111">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="99dd5-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="99dd5-112">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="99dd5-112">**.NET Framework versions:** Available since 2.0.</span></span>
