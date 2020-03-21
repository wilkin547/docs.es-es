---
title: Función SpawnDerivedClass (Referencia de API no administrada)
description: La función SpawnDerivedClass crea un nuevo objeto que deriva de un objeto.
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
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174854"
---
# <a name="spawnderivedclass-function"></a>Función SpawnDerivedClass
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
[en] Este parámetro no se utiliza.

`ptr`  
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppNewClass`  
[fuera] Recibe el puntero al nuevo objeto de definición de clase. Si se produce un error, no `ppNewClass` se devuelve un nuevo objeto y se deja sin modificar. Su valor `null`no puede ser .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Ha habido un fracaso general. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Se solicitó una operación no válida, como generar una clase de una instancia. |
| `WBEM_E_INCOMPLETE_CLASS` | La clase de origen no se definió o registró completamente con Administración de Windows, por lo que no se permite una nueva clase derivada. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` es `null`. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) método.

`ptr`debe ser una definición de clase que se convierta en la clase primaria del objeto generado. El objeto devuelto se convierte en una subclase del objeto actual.

El nuevo objeto `ppNewClass` devuelto se convierte automáticamente en una subclase del objeto actual. Este comportamiento no se puede invalidar. No hay ningún otro método por el cual se puedan crear subclases (clases derivadas).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
