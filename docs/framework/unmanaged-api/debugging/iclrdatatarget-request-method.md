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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179112"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request (Método)
Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, según lo definido por la implementación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  
 `reqCode`  
 [en] Definido por el usuario.  
  
 `inBufferSize`  
 [en] El tamaño del búfer de entrada, que se utiliza para la solicitud entrante.  
  
 `inBuffer`  
 [en] Un búfer que contiene la solicitud.  
  
 `outBufferSize`  
 [en] El tamaño del búfer de salida, que se utiliza para la respuesta.  
  
 `outBuffer`  
 [fuera] Un búfer que contiene la respuesta.  
  
## <a name="remarks"></a>Observaciones  
 El `Request` método facilita la adición de operaciones personalizadas no especificadas. Es decir, este método proporciona extensibilidad sin necesidad de revisión de la definición de interfaz.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
