---
title: Función GetNames (Referencia de API no administrada)
description: La función GetNames recupera los nombres de las propiedades de un objeto.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174958"
---
# <a name="getnames-function"></a>Función GetNames
Recupera un subconjunto o todos los nombres de las propiedades de un objeto.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[en] Este parámetro no se utiliza.

`ptr`  
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszQualifierName`  
[en] Puntero a un `LPCWSTR` válido que especifica un nombre de calificador que funciona como parte de un filtro. Para obtener más información, consulte la sección [Comentarios.](#remarks) Este parámetro puede ser `null`.

`lFlags`  
[en] Una combinación de campos de bits. Para obtener más información, consulte la sección [Comentarios.](#remarks)

`pQualifierValue`[en] Puntero a una `VARIANT` estructura válida inicializada en un valor de filtro. Este parámetro puede ser `null`.

`pstrNames`  
[fuera] Estructura `SAFEARRAY` que contiene nombres de propiedad. En la entrada, este parámetro `null`siempre debe ser un puntero a . Consulte la sección [Comentarios](#remarks) para obtener más información.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Ha habido un fracaso general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos o se especificó una combinación incorrecta de indicadores y parámetros. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) método.

El nombre devuelto se controla mediante una combinación de indicadores y parámetros. Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.  El filtro principal se `lFlags` especifica en el parámetro y los demás parámetros varían en función de él.

Los valores `lFlags` de marca en son campos de bits

Los indicadores que se `lEnumFlags` pueden pasar como argumento son campos de bits que se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código.  Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo. Sin embargo, las marcas del mismo grupo son mutuamente excluyentes.

| Banderas del Grupo 1 |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Devuelve todos los nombres de propiedad. `strQualifierName`y `pQualifierVal` no se utilizan. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Devuelve solo las propiedades que tienen un `strQualifierName` calificador del nombre especificado por el parámetro. Si se utiliza esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Devuelve solo las propiedades que no tienen un `strQualifierName` calificador del nombre especificado por el parámetro. Si se utiliza esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Devuelve solo las propiedades que tienen un `wszQualifierName` calificador del nombre especificado por el `pQualifierVal` parámetro y también tienen un valor idéntico al especificado por la estructura. Si se utiliza esta marca, `wszQualifierName` debe `pQualifierValue`especificar a y a . |

| Banderas del Grupo 2 |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Devuelve solo los nombres de las propiedades que definen las claves. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Devuelve solo los nombres de propiedad que son referencias a objetos. |

| Banderas del Grupo 3 |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Devuelve solo los nombres de propiedad que pertenecen a la clase más derivada. Excluir propiedades de las clases primarias. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Devuelve solo los nombres de propiedad que pertenecen a las clases primarias. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Devuelve solo los nombres de las propiedades del sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Devuelve solo los nombres de las propiedades que no son del sistema. |

La función siempre `SAFEARRAY` asigna un `WBEM_S_NO_ERROR`nuevo `pstrNames` si devuelve , y siempre se establece para que apunte a ella. La matriz devuelta puede tener 0 elementos si ninguna propiedad coincide con los filtros especificados. Si la función devuelve `WBM_S_NO_ERROR`un `SAFEARRAY` valor distinto de , no se devuelve una nueva estructura.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
