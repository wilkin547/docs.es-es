---
title: ICLRDataTarget3::GetExceptionRecord (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
ms.openlocfilehash: 0ea4546dcde4afa0a9db2e64ae34415d0973391b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860436"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>ICLRDataTarget3::GetExceptionRecord (Método)
Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino. Por ejemplo, para un destino de volcado de memoria, esto sería equivalente al registro de excepción que se `ExceptionParam` pasa a través del argumento a la función [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) en la biblioteca de ayuda de depuración de Windows (DbgHelp).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bufferSize`  
 [in] Tamaño del búfer de entrada, en bytes. Debe ser igual que `sizeof(` [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`.  
  
 `bufferUsed`  
 [out] Puntero a un tipo `ULONG32` que recibe el número de bytes escritos realmente en el búfer.  
  
 `buffer`  
 [out] Puntero a un búfer de memoria que recibe una copia del registro de excepciones. El registro de excepción se devuelve como un tipo de [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) .  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente. El registro de excepciones se ha copiado en el búfer de salida.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|No hay ningún registro de excepciones asociado al destino.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|El tamaño del búfer de entrada no es igual a `sizeof(MINIDUMP_EXCEPTION)`.|  
  
## <a name="remarks"></a>Comentarios  
 [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) es una estructura definida en DbgHelp. h e imagehlp. h en el Windows SDK.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataTarget3 (Interfaz)](iclrdatatarget3-interface.md)
- [Método GetExceptionContextRecord](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [Método GetExceptionThreadID](iclrdatatarget3-getexceptionthreadid-method.md)
