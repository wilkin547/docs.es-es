---
title: Función SpawnDerivedClass (referencia de la API no administrada)
description: La función SpawnDerivedClass crea un nuevo objeto que se deriva de un objeto.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f72e6b1c356077a94b141e40d6efe485e77e7a9e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120180"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass función)
Crea un objeto de clase recién derivado a partir de un objeto específico.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppNewClass`  
enuncia Recibe el puntero al nuevo objeto de definición de clase. Si se produce un error, no se devuelve un nuevo objeto y `ppNewClass` se deja sin modificar. Su valor no se puede `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Se solicitó una operación no válida, como la generación de una clase a partir de una instancia. |
| `WBEM_E_INCOMPLETE_CLASS` | La clase de origen no se definió por completo ni se registró con la administración de Windows, por lo que no se permite una nueva clase derivada. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | El valor de `ppNewClass` es `null`. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .

`ptr` debe ser una definición de clase que se convierte en la clase primaria del objeto generado. El objeto devuelto se convierte en una subclase del objeto actual.

El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual. Este comportamiento no se puede invalidar. No hay ningún otro método por el que se puedan crear subclases (clases derivadas).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
