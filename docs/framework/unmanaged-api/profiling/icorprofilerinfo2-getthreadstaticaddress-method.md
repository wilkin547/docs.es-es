---
title: ICorProfilerInfo2::GetThreadStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
ms.openlocfilehash: 2c98f67e20ea36d7fbbb31be2e3761594b674c36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868608"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a>ICorProfilerInfo2::GetThreadStaticAddress (Método)
Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a>Parameters  
 `classId`  
 de IDENTIFICADOR de la clase que contiene el campo estático de subproceso solicitado.  
  
 `fieldToken`  
 de Símbolo (token) de metadatos del campo estático de subproceso solicitado.  
  
 `threadId`  
 de IDENTIFICADOR del subproceso que es el ámbito del campo estático solicitado.  
  
 `ppAddress`  
 enuncia Puntero a la dirección del campo estático que está dentro del subproceso especificado.  
  
## <a name="remarks"></a>Notas  
 El método `GetThreadStaticAddress` puede devolver uno de los siguientes:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.  
  
- Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados. Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de que los perfiles de recolección de elementos no utilizados no asuman que son válidos.  
  
 Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)
