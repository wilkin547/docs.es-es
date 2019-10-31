---
title: Función GetNames (referencia de la API no administrada)
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
ms.openlocfilehash: 5b03ed6a68fbe288e93dedb4f425f1511563dfeb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102521"
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
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszQualifierName`  
de Puntero a una `LPCWSTR` válida que especifica un nombre de calificador que funciona como parte de un filtro. Para obtener más información, vea la sección [comentarios](#remarks) . Este parámetro puede ser `null`. 

`lFlags`  
de Combinación de campos de bits. Para obtener más información, vea la sección [comentarios](#remarks) .

`pQualifierValue`   
de Puntero a una estructura de `VARIANT` válida inicializada en un valor de filtro. Este parámetro puede ser `null`. 

`pstrNames`  
enuncia `SAFEARRAY` estructura que contiene los nombres de propiedad. En la entrada, este parámetro siempre debe ser un puntero a `null`. Vea la sección [comentarios](#remarks) para obtener más información. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos o se ha especificado una combinación incorrecta de marcas y parámetros. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .

El nombre devuelto se controla mediante una combinación de marcas y parámetros. Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.  El filtro principal se especifica en el parámetro `lFlags` y los demás parámetros varían en función de él.

Los valores de marca en `lFlags` son campos de bits

Las marcas que se pueden pasar como `lEnumFlags` argumento son campos de bits que se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.  Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo. Sin embargo, las marcas del mismo grupo se excluyen mutuamente. 

| Marcas de grupo 1 |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Devuelve todos los nombres de propiedad. `strQualifierName` y `pQualifierVal` no se usan. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Solo devuelve las propiedades que tienen un calificador del nombre especificado por el parámetro `strQualifierName`. Si se usa esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Solo devuelve las propiedades que no tienen un calificador del nombre especificado por el parámetro `strQualifierName`. Si se usa esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Solo devuelve las propiedades que tienen un calificador del nombre especificado por el parámetro `wszQualifierName` y que también tienen un valor idéntico al especificado por la estructura `pQualifierVal`. Si se usa esta marca, debe especificar un `wszQualifierName` y un `pQualifierValue`. |

| Marcas de grupo 2 |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Devuelve solo los nombres de las propiedades que definen las claves. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Devuelve solo los nombres de propiedad que son referencias a objetos. |

| Marcas de grupo 3 |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Devuelva solo los nombres de propiedad que pertenezcan a la clase más derivada. Excluya las propiedades de las clases primarias. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Solo se devuelven los nombres de propiedad que pertenezcan a las clases primarias. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Devuelve solo los nombres de las propiedades del sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Devuelve solo los nombres de las propiedades que no son del sistema. |

La función siempre asigna un nuevo `SAFEARRAY` si devuelve `WBEM_S_NO_ERROR`y `pstrNames` siempre se establece para que apunte a él. La matriz devuelta puede tener 0 elementos si ninguna propiedad coincide con los filtros especificados. Si la función devuelve un valor distinto de `WBM_S_NO_ERROR`, no se devuelve una nueva estructura de `SAFEARRAY`.
 
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
