---
title: GetPropertyHandle (función) (referencia de API no administrada)
description: GetPropertyHandle (función) devuelve un identificador único que identifica una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92d48caf7de873850135c7410a5e4b5861131212
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723243"
---
# <a name="getpropertyhandle-function"></a>Función GetPropertyHandle

Devuelve un controlador único que identifica una propiedad.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
[in] Este parámetro se usa.

`ptr`\
[in] Un puntero a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instancia.

`wszPropertyName`\
[in] Una-cadena terminada en null de caracteres codificados UTF16 que contiene el nombre de propiedad.

`pType`\
[out] Un puntero a un [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) miembro de enumeración que representa el tipo CIM de la propiedad.

`pHandle`\
[out] Un puntero a un entero que contiene el identificador de propiedad.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el nombre de propiedad especificado. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | La propiedad solicitada es de tipo son `CIM_OBJECT` o `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) método.

Puede usar este identificador para identificar las propiedades cuando se usa [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) métodos para leer o escribir los valores de propiedad.

Identificadores se pueden recuperar de las propiedades de todos los tipos de datos distinto `CIM_OBJECT` y `CIM_ARRAY`. Devuelve el trabajo de identificadores en todas las instancias de una clase.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)