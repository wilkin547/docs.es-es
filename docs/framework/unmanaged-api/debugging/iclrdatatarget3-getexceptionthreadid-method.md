---
description: 'Más información sobre: ICLRDataTarget3:: Getexceptionthreadid ((método)'
title: ICLRDataTarget3::GetExceptionThreadID (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 8202b6d83d0c81853111c5da7cfb8deec4d4e222
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794824"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>ICLRDataTarget3::GetExceptionThreadID (Método)

Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para obtener el identificador del subproceso que inició la excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `threadID`  
 [out] Identificador del subproceso que inició la excepción.  
  
## <a name="return-value"></a>Valor devuelto  

 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|No se pudo encontrar un identificador de subproceso válido para la excepción.|  
  
## <a name="remarks"></a>Observaciones  

 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget3 (Interfaz)](iclrdatatarget3-interface.md)
- [Método GetExceptionContextRecord](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [Método GetExceptionRecord](iclrdatatarget3-getexceptionrecord-method.md)
