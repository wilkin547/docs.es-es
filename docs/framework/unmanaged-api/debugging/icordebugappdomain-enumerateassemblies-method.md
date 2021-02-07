---
description: 'Más información acerca de: ICorDebugAppDomain:: EnumerateAssemblies ((método)'
title: ICorDebugAppDomain::EnumerateAssemblies (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
ms.openlocfilehash: 3ffa3180b80eac46e2d61019e4e4aa992f7c0e72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754269"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a>ICorDebugAppDomain::EnumerateAssemblies (Método)

Obtiene un enumerador para los ensamblados en el dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppAssemblies`  
 enuncia Un puntero a la dirección de un objeto ICorDebugAssemblyEnum que es el enumerador para los ensamblados en el dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
