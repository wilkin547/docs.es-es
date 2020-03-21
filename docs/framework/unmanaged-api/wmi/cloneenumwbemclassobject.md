---
title: Función CloneEnumWbemClassObject (Referencia de API no administrada)
description: La función CloneEnumWbemClassObject realiza una copia lógica de un enumerador.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175023"
---
# <a name="cloneenumwbemclassobject-function"></a>Función CloneEnumWbemClassObject
Realiza una copia lógica de un enumerador conservando su posición actual en una enumeración.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a>Parámetros

`ppEnum`\
[fuera] Recibe un puntero a un nuevo [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
[en] El nivel de autorización.

`impLevel`\
[en] El nivel de suplantación.

`pCurrentEnumWbemClassObject`\
[fuera] Puntero a la instancia de [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) que se va a clonar.

`strUser`\
[en] El nombre de usuario. Consulte la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`strPassword`\
[en] La contraseña. Consulte la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`strAuthority`\
[en] El nombre de dominio del usuario. Consulte la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Ha habido un fracaso general. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | El link de la llamada a procedimiento remoto (RPC) entre el proceso actual y el WMI ha fallado. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) método.

Este método hace sólo una copia de "mejor esfuerzo". Debido a la naturaleza dinámica de muchos objetos CIM, es posible que el nuevo enumerador no enumere el mismo conjunto de objetos que el enumerador de origen.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el [Método IEnumWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)

## <a name="requirements"></a>Requisitos
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils.idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
