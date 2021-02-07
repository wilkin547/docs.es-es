---
description: 'Más información acerca de: ServicePointManager. CloseConnectionGroups (método)'
title: Método ServicePointManager. CloseConnectionGroups (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 8cd1a1f0f4dbdaeaee117e6a7ae4219680363a6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699563"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="23bdd-103">ServicePointManager. CloseConnectionGroups (método)</span><span class="sxs-lookup"><span data-stu-id="23bdd-103">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="23bdd-104">Recorre en iteración todos los puntos de servicio y cierra los grupos de conexión que tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="23bdd-104">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="23bdd-105">Este método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="23bdd-105">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="23bdd-106">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="23bdd-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="23bdd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23bdd-107">Parameters</span></span>

<span data-ttu-id="23bdd-108">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="23bdd-108">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="23bdd-109">Nombre del grupo de conexiones que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="23bdd-109">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="23bdd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23bdd-110">Requirements</span></span>

<span data-ttu-id="23bdd-111">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="23bdd-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="23bdd-112">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="23bdd-112">**Assembly:** System (in System.dll)</span></span>
