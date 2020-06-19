---
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
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990499"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="165db-102">ServicePointManager. CloseConnectionGroups (método)</span><span class="sxs-lookup"><span data-stu-id="165db-102">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="165db-103">Recorre en iteración todos los puntos de servicio y cierra los grupos de conexión que tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="165db-103">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="165db-104">Este método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="165db-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="165db-105">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="165db-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="165db-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="165db-106">Parameters</span></span>

<span data-ttu-id="165db-107">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="165db-107">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="165db-108">Nombre del grupo de conexiones que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="165db-108">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="165db-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="165db-109">Requirements</span></span>

<span data-ttu-id="165db-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="165db-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="165db-111">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="165db-111">**Assembly:** System (in System.dll)</span></span>
