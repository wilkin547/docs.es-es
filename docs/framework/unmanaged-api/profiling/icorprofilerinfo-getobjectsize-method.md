---
title: ICorProfilerInfo::GetObjectSize (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42e86b1eac788b709432d39e320ebea49c696c14
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481715"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize (Método)
Obtiene el tamaño de un objeto especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Parámetros  
 `objectId`  
 [in] El identificador del objeto.  
  
 `pcSize`  
 [out] Puntero al tamaño del objeto, en bytes.  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
>  Este método está obsoleto. Devuelve COR_E_OVERFLOW para objetos de más de 4GB en plataformas de 64 bits. Use la [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) método en su lugar.  
  
 A menudo, distintos objetos de los mismos tipos tienen el mismo tamaño. Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.  
  
 El tamaño devuelto por la `GetObjectSize` método no incluye ningún relleno de alineación que puede aparecer después de que el objeto está en el montón de elementos no utilizados. Si usas el `GetObjectSize` método para avanzar el objeto en el montón de elementos no utilizados, agregar alineación relleno manualmente, según sea necesario.  
  
-   En Windows de 32 bits, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 y COR_PRF_GC_GEN_2 utilizan la alineación de 4 bytes y COR_PRF_GC_LARGE_OBJECT_HEAP usa la alineación de 8 bytes.  
  
-   En Windows de 64 bits, la alineación siempre tiene 8 bytes.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
