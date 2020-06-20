---
title: Exception. PrepForRemoting (método) (System)
description: Revise el método Exception. PrepForRemoting en .NET. El método agrega el seguimiento de la pila del servidor al mensaje antes de que se vuelva a producir la excepción en el cliente.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105259"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="fd3dc-104">Método Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="fd3dc-104">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="fd3dc-105">Conserva el seguimiento de la pila del servidor al anexarlo al mensaje antes de que se vuelva a producir la excepción en el sitio de llamada de cliente.</span><span class="sxs-lookup"><span data-stu-id="fd3dc-105">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="fd3dc-106">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="fd3dc-106">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="fd3dc-107">Esta instancia de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="fd3dc-107">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd3dc-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd3dc-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="fd3dc-109">El `Exception.PrepForRemoting` método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="fd3dc-109">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fd3dc-110">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="fd3dc-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd3dc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd3dc-111">Requirements</span></span>

<span data-ttu-id="fd3dc-112">**Espacio de nombres:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="fd3dc-112">**Namespace:** <xref:System></span></span>

<span data-ttu-id="fd3dc-113">**Ensamblado:** mscorlib.dll (en mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="fd3dc-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="fd3dc-114">**.NET Framework versiones:** Disponible desde 1,0.</span><span class="sxs-lookup"><span data-stu-id="fd3dc-114">**.NET Framework versions:** Available since 1.0.</span></span>
