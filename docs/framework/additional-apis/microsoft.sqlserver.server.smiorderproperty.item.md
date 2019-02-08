---
title: Propiedad SmiOrderProperty.Item (Microsoft.SqlServer.Server)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: cb2f6cb956f9571f9bd2ba7f86d79c5df6e72a15
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827739"
---
# <a name="smiorderpropertyitem-property"></a>SmiOrderProperty.Item Property

Obtiene el orden de las columnas de la entidad. El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso con SQL Server. Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.

## <a name="syntax"></a>Sintaxis

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a>Valor de propiedad

El orden de las columnas.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El `SmiOrderProperty.Item` propiedad es interna y no está pensada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:Microsoft.SqlServer.Server>

**Ensamblado:** System.Data (en System.Data.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.