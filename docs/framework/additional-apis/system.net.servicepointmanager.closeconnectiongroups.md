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
