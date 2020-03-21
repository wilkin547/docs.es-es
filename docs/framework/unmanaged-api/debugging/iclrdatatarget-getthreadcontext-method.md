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
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179181"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext (Método)
Obtiene el contexto de ejecución actual para el subproceso especificado en el proceso de destino. Los servicios de acceso a datos de Common Language Runtime llaman a este método.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `threadID`  
 [en] Identificador del sistema operativo de un subproceso en el proceso de destino.  
  
 `contextFlags`  
 [en] Indicadores que especifican qué partes del contexto se va a devolver. La implementación devolverá al menos estas partes del contexto.  
  
 `contextSize`  
 [en] El tamaño del contexto.  
  
 `context`  
 [fuera] Puntero a un búfer en el que se va a colocar el contexto.  
  
 Los datos `context` del búfer deben tener el formato `CONTEXT` de la estructura Win32. El contexto especifica datos de registro específicos del procesador, por lo que la definición de la estructura Win32 `CONTEXT` depende de la arquitectura del procesador. Consulte el archivo de encabezado WinNT.h para `CONTEXT` obtener la definición de la estructura Win32.  
  
## <a name="remarks"></a>Observaciones  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
