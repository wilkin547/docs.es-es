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
# <a name="servicepointmanagercloseconnectiongroups-method"></a>ServicePointManager. CloseConnectionGroups (método)

Recorre en iteración todos los puntos de servicio y cierra los grupos de conexión que tienen el nombre especificado.

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> Este método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="parameters"></a>Parámetros

`connectionGroupName` <xref:System.String>

Nombre del grupo de conexiones que se va a cerrar.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
