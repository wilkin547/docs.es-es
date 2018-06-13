---
title: ICorProfilerInfo3::GetRuntimeInformation (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67e1d20f7faf38fa37083f1a5b1cc0c1060b7a32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461573"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation (Método)
Proporciona información de versión de common language runtime (CLR) que se está perfilando.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pClrInstanceId`  
 [out] Identificador representativo de una instancia CLR de ejecución en un proceso. Este es el mismo que el `ClrInstanceID` que informa el seguimiento de eventos para eventos de inicio de Windows (ETW).  
  
 `pRuntimeType`  
 [out] El tipo en tiempo de ejecución. Este parámetro devuelve `COR_PRF_DESKTOP_CLR` para la versión de CLR, el escritorio o `COR_PRF_CORE_CLR` para la versión básica del CLR usada en Silverlight.  
  
 `pMajorVersion`  
 [out] El número de versión principal de CLR.  
  
 `pMinorVersion`  
 [out] El número de versión secundaria del CLR.  
  
 `pBuildVersion`  
 [out] El número de versión de compilación de CLR.  
  
 `pQFEVersion`  
 [out] El número de versión de CLR que está asociado a una actualización de software.  
  
 `cchVersionString`  
 [in] La longitud, en caracteres, del búfer que `szVersionString` apunta a.  
  
 `pcchVersionString`  
 [out] La longitud, en caracteres, de `szVersionString`.  
  
 `szVersionString`  
 [out] La cadena de versión CLR.  
  
## <a name="remarks"></a>Comentarios  
 Se puede pasar null para cualquier parámetro. Sin embargo, `pcchVersionString` no puede ser null a menos que `szVersionString` también es null.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
