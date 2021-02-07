---
description: 'Más información sobre: WebHeaderCollection. AddInternal (método)'
title: Método WebHeaderCollection. AddInternal (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7bc84f84e6656dba5230b627fe9decfc4e0b4746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699485"
---
# <a name="webheadercollectionaddinternal-method"></a>WebHeaderCollection. AddInternal, método

Agrega un nuevo encabezado con el nombre y el valor especificados a la colección, omitiendo las comprobaciones.

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> Este método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="parameters"></a>Parámetros

- `name` <xref:System.String>

  Nombre del encabezado.

- `value` <xref:System.String>

  Valor del encabezado.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
