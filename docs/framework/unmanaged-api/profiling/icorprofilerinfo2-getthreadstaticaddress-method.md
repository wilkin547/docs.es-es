---
description: 'Más información acerca de: ICorProfilerInfo2:: Getthreadstaticaddress ((método)'
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
ms.openlocfilehash: bab4190f3751967031806dccbea2fdf6add73f6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647060"
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
  
## <a name="parameters"></a>Parámetros  

 `classId`  
 de IDENTIFICADOR de la clase que contiene el campo estático de subproceso solicitado.  
  
 `fieldToken`  
 de Símbolo (token) de metadatos del campo estático de subproceso solicitado.  
  
 `threadId`  
 de IDENTIFICADOR del subproceso que es el ámbito del campo estático solicitado.  
  
 `ppAddress`  
 enuncia Puntero a la dirección del campo estático que está dentro del subproceso especificado.  
  
## <a name="remarks"></a>Observaciones  

 El `GetThreadStaticAddress` método puede devolver uno de los siguientes:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.  
  
- Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados. Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de que los perfiles de recolección de elementos no utilizados no asuman que son válidos.  
  
 Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
