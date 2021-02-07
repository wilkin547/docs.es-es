---
description: 'Más información acerca de: ICorProfilerInfo2:: Getappdomainstaticaddress ((método)'
title: ICorProfilerInfo2::GetAppDomainStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 4ef8511e75a18f7626fa7a30ea194140de051bb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753242"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>ICorProfilerInfo2::GetAppDomainStaticAddress (Método)

Obtiene la dirección del campo estático del dominio de aplicación especificado que está en el ámbito del dominio de aplicación especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parámetros  

 `classId`  
 de IDENTIFICADOR de clase de la clase que contiene el campo estático de dominio de aplicación solicitado.  
  
 `fieldToken`  
 de El símbolo (token) de metadatos del campo estático de dominio de aplicación solicitado.  
  
 `appDomainId`  
 de IDENTIFICADOR del dominio de aplicación que es el ámbito del campo estático solicitado.  
  
 `ppAddress`  
 enuncia Puntero a la dirección del campo estático que se encuentra dentro del dominio de aplicación especificado.  
  
## <a name="remarks"></a>Observaciones  

 El `GetAppDomainStaticAddress` método puede devolver uno de los siguientes:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.  
  
- Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados. Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.  
  
 Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
