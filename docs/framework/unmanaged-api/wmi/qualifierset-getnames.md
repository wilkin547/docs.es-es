---
title: Función QualifierSet_GetNames (referencia de la API no administrada)
description: La función QualifierSet_GetNames recupera los nombres de los calificadores de un objeto o propiedad.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141695"
---
# <a name="qualifierset_getnames-function"></a>QualifierSet_GetNames función)

Recupera los nombres de todos los calificadores o de determinados calificadores que están disponibles en el objeto o propiedad actual.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`\
de Uno de los siguientes marcadores o valores que especifica los nombres que se van a incluir en la enumeración.

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devuelve los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Devuelve solo los nombres de calificadores específicos de la propiedad o el objeto actual. <br/> En el caso de una propiedad: solo se devuelven los calificadores específicos de la propiedad (incluidas las invalidaciones), y no los calificadores propagados a partir de la definición de clase. <br/> Para una instancia de: solo se devuelven nombres de calificador específicos de la instancia. <br/> Para una clase: solo se devuelven los calificadores específicos de la clase que se deriva.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Devuelve solo los nombres de los calificadores propagados desde otro objeto. <br/> Para una propiedad: solo se devuelven los calificadores propagados a esta propiedad desde la definición de clase, y no los de la propia propiedad. <br/> Para una instancia de: solo se devuelven los calificadores propagados desde la definición de clase. <br/> Para una clase: solo se devuelven los nombres de calificador heredados de las clases primarias. |

`pstrNames`\
enuncia Nuevo `SAFEARRAY` que contiene los nombres solicitados. La matriz puede tener 0 elementos. Si se produce un error, no se devuelve un nuevo `SAFEARRAY`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .

Una vez que haya recuperado los nombres de calificador, puede tener acceso a cada calificador por nombre llamando a la función [QualifierSet_Get](qualifierset-get.md) .

No es un error que un objeto dado tenga calificadores cero, por lo que el número de cadenas de `pstrNames` en la devolución puede ser 0, aunque la función devuelva `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
