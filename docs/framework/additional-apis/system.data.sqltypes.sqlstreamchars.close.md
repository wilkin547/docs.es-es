---
title: Método SqlStreamChars. Close (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c33c60842d181be7011528ca7550f3d09f291f43
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395630"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="8cb02-102">SqlStreamChars. Close (método)</span><span class="sxs-lookup"><span data-stu-id="8cb02-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="8cb02-103">Cierra la secuencia actual y libera todos los recursos del sistema asociados a la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8cb02-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="8cb02-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="8cb02-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="8cb02-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cb02-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="8cb02-106"> En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="8cb02-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="8cb02-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8cb02-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="8cb02-108">El método `SqlStreamChars.Close` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="8cb02-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8cb02-109">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="8cb02-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="8cb02-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cb02-110">Requirements</span></span>

<span data-ttu-id="8cb02-111">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="8cb02-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="8cb02-112">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="8cb02-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="8cb02-113">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="8cb02-113">**.NET Framework versions:** Available since 2.0.</span></span>
