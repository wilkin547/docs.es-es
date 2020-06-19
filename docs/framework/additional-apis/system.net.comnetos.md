---
title: Clase comnetos (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990520"
---
# <a name="comnetos-class"></a><span data-ttu-id="c999c-102">Clase comnetos</span><span class="sxs-lookup"><span data-stu-id="c999c-102">ComNetOS class</span></span>

<span data-ttu-id="c999c-103">Proporciona información sobre el sistema operativo actual, como su tipo de instalación y versión (cliente o servidor).</span><span class="sxs-lookup"><span data-stu-id="c999c-103">Provides information about the current operating system, such as its version and installation type (client or server).</span></span> <span data-ttu-id="c999c-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="c999c-104">This class cannot be inherited.</span></span>
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> <span data-ttu-id="c999c-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="c999c-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c999c-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="c999c-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="iswin7orlater-field"></a><span data-ttu-id="c999c-107">Campo IsWin7orLater</span><span class="sxs-lookup"><span data-stu-id="c999c-107">IsWin7orLater field</span></span>

<span data-ttu-id="c999c-108">Especifica si la versión del sistema operativo es Windows 7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="c999c-108">Specifies whether the operating system version is Windows 7 or later.</span></span>

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a><span data-ttu-id="c999c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c999c-109">Requirements</span></span>

<span data-ttu-id="c999c-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c999c-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c999c-111">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="c999c-111">**Assembly:** System (in System.dll)</span></span>
