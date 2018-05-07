---
title: ICLRDataTarget::Request (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc79277c75118b11766e66137284bd5655eed091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request (Método)
Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, tal como se define por la implementación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `reqCode`  
 [in] Definido por el usuario.  
  
 `inBufferSize`  
 [in] El tamaño del búfer de entrada, que se utiliza para la solicitud entrante.  
  
 `inBuffer`  
 [in] Un búfer que contiene la solicitud.  
  
 `outBufferSize`  
 [in] El tamaño del búfer de salida, que se utiliza para la respuesta.  
  
 `outBuffer`  
 [out] Un búfer que contiene la respuesta.  
  
## <a name="remarks"></a>Comentarios  
 El `Request` método facilita la adición de las operaciones personalizadas no especificadas. Es decir, este método proporciona extensibilidad sin necesidad de revisión de la definición de interfaz.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
