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
ms.openlocfilehash: b8e503af11fa1d02aac2ec83edde0ffbd562d8e5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496404"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation (Método)
Proporciona información de versión sobre el Common Language Runtime (CLR) del que se está generando el archivo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  
 `pClrInstanceId`  
 enuncia IDENTIFICADOR representativo de una instancia de CLR en ejecución en un proceso. Es lo mismo `ClrInstanceID` que los informes de eventos de inicio de seguimiento de eventos para Windows (ETW).  
  
 `pRuntimeType`  
 enuncia El tipo en tiempo de ejecución. Este parámetro devuelve `COR_PRF_DESKTOP_CLR` para la versión de escritorio de CLR, o `COR_PRF_CORE_CLR` para la versión principal de CLR que se usa en Silverlight.  
  
 `pMajorVersion`  
 enuncia Número de versión principal de CLR.  
  
 `pMinorVersion`  
 enuncia Número de versión secundaria de CLR.  
  
 `pBuildVersion`  
 enuncia Número de versión de compilación de CLR.  
  
 `pQFEVersion`  
 enuncia El número de versión de CLR que está asociado a una actualización de software.  
  
 `cchVersionString`  
 de La longitud, en caracteres, del búfer al que `szVersionString` apunta.  
  
 `pcchVersionString`  
 enuncia La longitud, en caracteres, de `szVersionString` .  
  
 `szVersionString`  
 enuncia Cadena de versión de CLR.  
  
## <a name="remarks"></a>Comentarios  
 Puede pasar null para cualquier parámetro. Sin embargo, `pcchVersionString` no puede ser null a menos que `szVersionString` también sea NULL.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
