---
title: ICorDebugILFrame::EnumerateArguments (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 9b0bc59b67b5d4b2184733f22616433bf33be616
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703231"
---
# <a name="icordebugilframeenumeratearguments-method"></a>ICorDebugILFrame::EnumerateArguments (Método)

Obtiene un enumerador para los argumentos de este marco.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppValueEnum`  
 enuncia Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de los argumentos de este marco.  
  
## <a name="remarks"></a>Comentarios  

 `EnumerateArguments` Obtiene un enumerador que puede enumerar los argumentos disponibles en el marco de llamada representado por este objeto ICorDebugILFrame. La lista incluirá argumentos que son [vararg](/cpp/windows/vararg) (es decir, un número variable de argumentos), así como argumentos que no son `vararg` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
