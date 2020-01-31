---
title: ICLRDataTarget::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: b5f6a830cbe601443f03cd91a356c7e49450e7f3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793730"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext (Método)
Obtiene el contexto de ejecución actual para el subproceso dado en el proceso de destino. El servicio de acceso a datos de Common Language Runtime llama a este método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 de Identificador del sistema operativo de un subproceso en el proceso de destino.  
  
 `contextFlags`  
 de Marcas que especifican qué partes del contexto se van a devolver. La implementación devolverá al menos estas partes del contexto.  
  
 `contextSize`  
 de Tamaño del contexto.  
  
 `context`  
 enuncia Puntero a un búfer en el que se va a colocar el contexto.  
  
 Los datos del búfer de `context` deben tener el formato de la estructura de `CONTEXT` de Win32. El contexto especifica datos de registro específicos del procesador, por lo que la definición de la estructura de `CONTEXT` de Win32 depende de la arquitectura del procesador. Consulte el archivo de encabezado Winnt. h para ver la definición de la estructura de `CONTEXT` de Win32.  
  
## <a name="remarks"></a>Notas  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
