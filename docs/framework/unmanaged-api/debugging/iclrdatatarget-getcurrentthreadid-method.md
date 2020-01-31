---
title: ICLRDataTarget::GetCurrentThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: 35515d7c2b82ec2c42461406363964e0b60eb243
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785469"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a>ICLRDataTarget::GetCurrentThreadID (Método)
Obtiene el identificador del sistema operativo para el subproceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 enuncia Puntero al identificador del sistema operativo del subproceso actual para el proceso de destino.  
  
## <a name="remarks"></a>Notas  
 Si no hay ningún subproceso actual para el proceso de destino, se puede producir un error en el método `GetCurrentThreadID`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
