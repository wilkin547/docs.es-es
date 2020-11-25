---
title: ICorDebugILFrame::EnumerateLocalVariables (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 968ceec53aade3d04c500c8247d397ffb71382c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703211"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a>ICorDebugILFrame::EnumerateLocalVariables (Método)

Obtiene un enumerador para las variables locales de este marco.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppValueEnum`  
 [out] Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de las variables locales en este marco.  
  
## <a name="remarks"></a>Comentarios  

 `EnumerateLocalVariables` Obtiene un enumerador que puede enumerar las variables locales disponibles en el marco de llamada representado por este objeto ICorDebugILFrame. La lista puede no incluir todas las variables locales de la función en ejecución, porque algunas de ellas pueden no estar activas.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
