---
title: Función PutMethod (referencia de la API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2b41cbbade9da5c2095309b9039b8ce2758f6f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798361"
---
# <a name="putmethod-function"></a>PutMethod función)
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
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`  
de Nombre del método que se va a crear. 

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pSignatureIn`  
de Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene `in` los parámetros del método. Se omite este parámetro si se establece `null`en.  

`pSignatureOut`  
de  Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene `out` los parámetros del método. Se omite este parámetro si se establece `null`en.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | El `[in, out]` parámetro de método especificado en los objetos *pInSignature* y *pOutSignature* tiene calificadores diferentes.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Falta la especificación del calificador de **identificador** en un parámetro de método. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie de IDENTIFICADOres que se asigna a los parámetros de método no es consecutiva o no comienza en 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | El valor devuelto para un método tiene un calificador de **identificador** . |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Se intentó reutilizar un nombre de método existente de una clase primaria y las firmas no coincidían. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

Esta llamada al método solo se admite `ptr` si es una definición de clase CIM. La manipulación de métodos no está disponible en los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que señalan a las instancias CIM.

Los usuarios no pueden crear métodos con nombres que comiencen o terminen con un carácter de subrayado. Está reservado para las propiedades y clases del sistema.

Para un método, los `in` parámetros `out` y se describen como propiedades en objetos [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

Un `[in/out]` parámetro se puede definir agregando la misma propiedad a ambos objetos a los que apuntan `pOutSignature` los `pInSignature` parámetros y. En este caso, las propiedades comparten el mismo valor de calificador de **identificador** .

Cada propiedad de un objeto de clase [__Parameters](/windows/desktop/WmiSdk/--parameters) que `ReturnValue` no sea debe tener un calificador de **identificador** , un valor numérico basado en cero que identifique el orden en el que aparecen los parámetros. Dos parámetros no pueden tener el mismo valor de **identificador** y no se puede omitir ningún valor de **identificador** . Si se produce alguna de las `PutMethod` condiciones, `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`la función devuelve.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el método [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
