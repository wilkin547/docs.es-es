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
ms.openlocfilehash: e3d167be9a4091ae57a3283424186142e90ca7a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868556"
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
  
## <a name="parameters"></a>Parameters  
 `pClrInstanceId`  
 enuncia IDENTIFICADOR representativo de una instancia de CLR en ejecución en un proceso. Esto es lo mismo que el `ClrInstanceID` que los informes de eventos de inicio de seguimiento de eventos para Windows (ETW).  
  
 `pRuntimeType`  
 enuncia El tipo en tiempo de ejecución. Este parámetro devuelve `COR_PRF_DESKTOP_CLR` para la versión de escritorio de CLR o `COR_PRF_CORE_CLR` para la versión básica de CLR que se usa en Silverlight.  
  
 `pMajorVersion`  
 enuncia Número de versión principal de CLR.  
  
 `pMinorVersion`  
 enuncia Número de versión secundaria de CLR.  
  
 `pBuildVersion`  
 enuncia Número de versión de compilación de CLR.  
  
 `pQFEVersion`  
 enuncia El número de versión de CLR que está asociado a una actualización de software.  
  
 `cchVersionString`  
 de La longitud, en caracteres, del búfer al que apunta `szVersionString`.  
  
 `pcchVersionString`  
 enuncia La longitud, en caracteres, de `szVersionString`.  
  
 `szVersionString`  
 enuncia Cadena de versión de CLR.  
  
## <a name="remarks"></a>Notas  
 Puede pasar null para cualquier parámetro. Sin embargo, `pcchVersionString` no puede ser null a menos que `szVersionString` también sea NULL.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo3 (interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
