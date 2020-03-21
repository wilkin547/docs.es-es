---
title: Función PutMethod (Referencia de API no administrada)
description: La función PutMethod crea un método.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174919"
---
# <a name="putmethod-function"></a>Función PutMethod
Crea un método.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[en] Este parámetro no se utiliza.

`ptr`  
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`  
[en] El nombre del método que se ha creado.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pSignatureIn`  
[en] Puntero a una copia de la clase `in` de sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) que contiene los parámetros del método. Este parámetro se omite `null`si se establece en .  

`pSignatureOut`  
[en]  Puntero a una copia de la clase `out` de sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) que contiene los parámetros del método. Este parámetro se omite `null`si se establece en .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | El `[in, out]` parámetro de método especificado en los objetos *pInSignature* y *pOutSignature* tiene calificadores diferentes.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | A un parámetro de método le falta la especificación del calificador **ID.** |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie de ID asignada a los parámetros del método no es consecutiva o no comienza en 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | El valor devuelto para un método tiene un calificador **de identificador.** |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Se ha intentado reutilizar un nombre de método existente de una clase primaria y las firmas no coinciden. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente. |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.

Esta llamada al método `ptr` solo se admite si es una definición de clase CIM. La manipulación de métodos no está disponible en los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que apuntan a instancias de CIM.

Los usuarios no pueden crear métodos con nombres que comiencen o terminen con un carácter de subrayado. Esto está reservado para las clases y propiedades del sistema.

Para un método, los `in` parámetros y `out` se describen como propiedades en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objetos.

Un `[in/out]` parámetro se puede definir agregando la misma `pInSignature` propiedad `pOutSignature` a ambos objetos a los que apunta el y parámetros. En este caso, las propiedades comparten el mismo valor de calificador de **ID.**

Cada propiedad de un objeto `ReturnValue` de clase [__Parameters](/windows/desktop/WmiSdk/--parameters) distinto de debe tener un calificador de **identificador,** un valor numérico de base cero que identifica el orden en el que aparecen los parámetros. No hay dos parámetros que puedan tener el mismo valor **de ID** y no se puede omitir ningún valor de **ID.** Si se produce `PutMethod` alguna `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`condición, la función devuelve .

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
