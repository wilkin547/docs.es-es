---
description: 'Más información acerca de: ICLRDataTarget:: Request (método)'
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
ms.openlocfilehash: 75c400a51a2fdaf0044d85b5f483d783fae4628b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712173"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request (Método)

Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.  
  
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
 de Definido por el usuario.  
  
 `inBufferSize`  
 de Tamaño del búfer de entrada, que se usa para la solicitud entrante.  
  
 `inBuffer`  
 de Búfer que contiene la solicitud.  
  
 `outBufferSize`  
 de Tamaño del búfer de salida, que se usa para la respuesta.  
  
 `outBuffer`  
 enuncia Búfer que contiene la respuesta.  
  
## <a name="remarks"></a>Observaciones  

 El `Request` método facilita la adición de operaciones personalizadas no especificadas. Es decir, este método proporciona extensibilidad sin necesidad de revisar la definición de la interfaz.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (Interfaz)](iclrdatatarget-interface.md)
