---
title: Interfaz ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: e90952a92c408762a98a2bfcb91b6aeb72052df1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791217"
---
# <a name="icordebugtype2-interface"></a>Interfaz ICorDebugType2
Extiende la interfaz ICorDebugType para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).  
  
## <a name="methods"></a>Métodos  
  
|Método||  
|------------|-|  
|[GetTypeID (método)](icordebugtype2-gettypeid-method.md)|Obtiene un [COR_TYPEID](cor-typeid-structure.md) para este tipo.|  
  
## <a name="remarks"></a>Notas  
 Esta interfaz es una extensión lógica de la interfaz ICorDebugType.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="example"></a>Ejemplo  
 En el fragmento de código siguiente se muestra el uso del método [ICorDebugType2:: GetTypeID](icordebugtype2-gettypeid-method.md) .  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
