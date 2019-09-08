---
title: Función GetPropertyQualifierSet (referencia de la API no administrada)
description: La función GetPropertyQualifierSet recupera el calificador establecido para una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798471"
---
# <a name="getpropertyqualifierset-function"></a>GetPropertyQualifierSet función)

Recupera el calificador establecido para una propiedad específica.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszMethod`\
de Nombre de la propiedad. `wszProperty`debe apuntar a un `LPCWSTR`válido.

`ppQualSet`\
enuncia Recibe el puntero de interfaz que permite el acceso a los calificadores de la propiedad. El valor de `ppQualSet` no puede ser `null`. Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece en apuntar `null`a.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | El método especificado no existe. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro es `null`. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | La función intenta obtener los calificadores de una propiedad del sistema. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) .

Solo se admite una llamada a esta función si el objeto actual es una definición de clase CIM. La manipulación de métodos no está disponible para los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que señalan a las instancias CIM.

Dado que cada método puede tener sus propios calificadores, el [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.

Dado que las propiedades del sistema no tienen calificadores, `WBEM_E_SYSTEM_PROPERTY` la función devuelve si intenta obtener un puntero [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) para una propiedad del sistema.

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
