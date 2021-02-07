---
description: 'Más información acerca de: ICorDebugArrayValue:: Getdimensions ((método)'
title: ICorDebugArrayValue::GetDimensions (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: 007a48891a01e5779e3f9ef10cec720d6647c8f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723106"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>ICorDebugArrayValue::GetDimensions (Método)

Obtiene el número de elementos de cada dimensión de esta matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cdim`  
 de Número de dimensiones de este objeto ICorDebugArrayValue.  
  
 Este valor también es el tamaño de la `dims` matriz porque su tamaño es igual al número de dimensiones del `ICorDebugArrayValue` objeto.  
  
 `dims`  
 enuncia Matriz de enteros, cada uno de los cuales especifica el número de elementos de una dimensión en este `ICorDebugArrayValue` objeto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
