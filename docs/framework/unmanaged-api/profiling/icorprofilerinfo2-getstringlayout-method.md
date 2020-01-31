---
title: ICorProfilerInfo2::GetStringLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868621"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout (Método)
Obtiene información sobre la distribución de un objeto de cadena. Este método está en desuso en el .NET Framework 4 y se ha sustituido por el método [ICorProfilerInfo3:: GetStringLayout2 (](icorprofilerinfo3-getstringlayout2-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parameters  
 `pBufferLengthOffset`  
 enuncia Puntero al desplazamiento de la ubicación, en relación con el puntero de `ObjectID`, que almacena la longitud de la cadena. La longitud se almacena como `DWORD`.  
  
> [!NOTE]
> Este parámetro devuelve la longitud de la cadena en sí, no la longitud del búfer. La longitud del búfer ya no está disponible.  
  
 `PStringLengthOffset`  
 enuncia Puntero al desplazamiento de la ubicación, en relación con el puntero de `ObjectID`, que almacena la longitud de la propia cadena. La longitud se almacena como `DWORD`.  
  
 `pBufferOffset`  
 enuncia Puntero al desplazamiento del búfer, relativo al puntero de `ObjectID`, que almacena la cadena de caracteres anchos.  
  
## <a name="remarks"></a>Notas  
 El método `GetStringLayout` obtiene los desplazamientos, con relación al puntero `ObjectID`, de las ubicaciones en las que se almacenan los elementos siguientes:  
  
- Longitud del búfer de la cadena.  
  
- La longitud de la propia cadena.  
  
- Búfer que contiene la cadena real de caracteres anchos.  
  
 Las cadenas pueden terminar en NULL.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)
