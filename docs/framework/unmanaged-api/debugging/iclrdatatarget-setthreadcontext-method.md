---
title: ICLRDataTarget::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: cdf5776e1ac9907e63aba0e0d400e48aff683d51
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785296"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext (Método)
Establece el contexto actual del subproceso especificado en el proceso de destino. Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 de Identificador del sistema operativo de un subproceso en el proceso de destino.  
  
 `contextSize`  
 de Tamaño del contexto.  
  
 `context`  
 de Puntero a un búfer que contiene el contexto.  
  
 Los datos del búfer de `context` estarán en el formato de la estructura de `CONTEXT` de Win32. El contexto especifica datos de registro específicos del procesador, por lo que la definición de la estructura de `CONTEXT` de Win32 depende de la arquitectura del procesador. Consulte el archivo de encabezado Winnt. h para ver la definición de la estructura de `CONTEXT` de Win32.  
  
## <a name="remarks"></a>Notas  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
