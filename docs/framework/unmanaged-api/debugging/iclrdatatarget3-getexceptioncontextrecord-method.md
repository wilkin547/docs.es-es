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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b43ab8cdeff3866bb51e8634f367cf86ee483d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089236"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>ICLRDataTarget3::GetExceptionContextRecord (Método)
Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino. Por ejemplo, para un destino de volcado de memoria, esto sería equivalente al registro de contexto pasado a través de la `ExceptionParam` argumento para el [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) función de Windows Debug Help Library (DbgHelp).  
  
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
 [out] Puntero a un búfer de memoria que recibe una copia del registro del contexto. El registro de excepciones se devuelve como un [contexto](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) tipo.  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente. El registro de contexto se ha copiado en el búfer de salida.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|No hay ningún registro de contexto asociado al destino.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|El tamaño del búfer de entrada no es suficientemente grande para alojar el registro de contexto.|  
  
## <a name="remarks"></a>Comentarios  
 [CONTEXTO](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) es una estructura específica de la plataforma definida en encabezados proporcionados por el SDK de Windows.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [GetExceptionRecord (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [GetExceptionThreadID (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
