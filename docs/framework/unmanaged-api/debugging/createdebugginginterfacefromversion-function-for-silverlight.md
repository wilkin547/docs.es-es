---
description: 'Más información sobre: función CreateDebuggingInterfaceFromVersion (para Silverlight'
title: CreateDebuggingInterfaceFromVersion (Función para Silverlight)
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 8c61593f2e912260ecca65efce9f905ce56e88dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801454"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>CreateDebuggingInterfaceFromVersion (Función para Silverlight)

Acepta una cadena de versión de Common Language Runtime (CLR) que se devuelve desde la [función createversionstringfrommodule (](createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente (normalmente, [ICorDebug](icordebug-interface.md)).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szDebuggeeVersion`\
 de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](createversionstringfrommodule-function.md).  
  
 `ppCordb`\
 [out] Puntero a un puntero a un objeto COM (`IUnknown`). Este objeto se convertirá en un objeto [ICorDebug](icordebug-interface.md) antes de que se devuelva.  
  
## <a name="return-value"></a>Valor devuelto

 `S_OK`\
 `ppCordb` hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](icordebug-interface.md) .  
  
 `E_INVALIDARG`\
 `szDebuggeeVersion` o `ppCordb` es nulo.  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 Componente que es necesario para que no se pueda encontrar la depuración de CLR. No se encontró _mscordbi.dll_ o _mscordaccore.dll_ en el mismo directorio que el CoreCLR.dll de destino.  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.  
  
 `E_FAIL` (u otros `E_` códigos de retorno) \
 No se puede devolver una [interfaz ICorDebug](icordebug-interface.md).  
  
## <a name="remarks"></a>Observaciones

 La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.  
  
## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim.dll  
  
 **.NET Framework versiones:** 3,5 SP1
