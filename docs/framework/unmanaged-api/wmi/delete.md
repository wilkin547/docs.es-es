---
title: Función Delete (referencia de la API no administrada)
description: La función Delete elimina la propiedad especificada y todos sus calificadores de una definición de clase CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6b8f287be831702dd31a8335f9b2f6447bcee540
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127662"
---
# <a name="delete-function"></a>Función Delete

Elimina la propiedad especificada y todos sus calificadores de una definición de clase CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
de Nombre de la propiedad que se va a eliminar. `wszName` debe ser un puntero a una `LPCWSTR`válida.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | No se puede eliminar la propiedad. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` no es válido. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La propiedad especificada no existe. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria para completar la operación. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | La propiedad se hereda de una clase base. |
| `WBEM_E_SYSTEM_PROPERTY` | | La propiedad es una propiedad del sistema. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | La función eliminó un valor predeterminado de invalidación para la clase actual. Se ha reactivado el valor predeterminado de esta propiedad en la clase primaria. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject::D iminar](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
