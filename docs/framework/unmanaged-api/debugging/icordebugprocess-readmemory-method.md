---
title: ICorDebugProcess::ReadMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178662"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory (Método)
Lee un área de memoria especificada para este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [en] Valor `CORDB_ADDRESS` que especifica la dirección base de la memoria que se va a leer.  
  
 `size`  
 [en] El número de bytes que se leerán de la memoria.  
  
 `buffer`  
 [fuera] Un búfer que recibe el contenido de la memoria.  
  
 `read`  
 [fuera] Puntero al número de bytes transferidos al búfer especificado.  
  
## <a name="remarks"></a>Observaciones  
 El `ReadMemory` método está pensado principalmente para ser utilizado por la depuración de interoperabilidad para inspeccionar las regiones de memoria que está utilizando la parte no administrada del depurador. Este método también se puede utilizar para leer código de lenguaje intermedio de Microsoft (MSIL) y código nativo compilado por JIT.  
  
 Los puntos de interrupción administrados se `buffer` quitarán de los datos que se devuelven en el parámetro. No se realizarán ajustes para los puntos de interrupción nativos establecidos por [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 No se realiza el almacenamiento en caché de la memoria de proceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
