---
title: ICLRDataTarget3::GetExceptionContextRecord (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
ms.openlocfilehash: 5a090b7c4801e6b2baf56f1d80e7e52f2aaa9293
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112295"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>ICLRDataTarget3::GetExceptionContextRecord (Método)
Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino. Por ejemplo, para un destino de volcado de memoria, esto sería equivalente al registro de contexto que se pasa a través del argumento `ExceptionParam` a la función [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) de la biblioteca de ayuda de depuración de Windows (DbgHelp).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bufferSize`  
 [in] Tamaño del búfer de entrada, en bytes. Debe ser suficientemente grande como para contener el registro de contexto.  
  
 `bufferUsed`  
 [out] Puntero a un tipo `ULONG32` que recibe el número de bytes escritos realmente en el búfer.  
  
 `buffer`  
 [out] Puntero a un búfer de memoria que recibe una copia del registro del contexto. El registro de excepciones se devuelve como un tipo de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente. El registro de contexto se ha copiado en el búfer de salida.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|No hay ningún registro de contexto asociado al destino.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|El tamaño del búfer de entrada no es suficientemente grande para alojar el registro de contexto.|  
  
## <a name="remarks"></a>Comentarios  
 El [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) es una estructura específica de la plataforma que se define en los encabezados proporcionados por el Windows SDK.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [GetExceptionRecord (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [GetExceptionThreadID (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
