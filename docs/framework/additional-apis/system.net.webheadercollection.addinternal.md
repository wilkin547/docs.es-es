---
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
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990494"
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
