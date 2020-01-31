---
title: CreateDebuggingInterfaceFromVersion (Función para Silverlight)
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 85b5a5a630f399d0e036de434365e2e4f8f02dea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793835"
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
  
## <a name="parameters"></a>Parameters  
 `szDebuggeeVersion`  
 de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](createversionstringfrommodule-function.md).  
  
 `ppCordb`  
 [out] Puntero a un puntero a un objeto COM (`IUnknown`). Este objeto se convertirá en un objeto [ICorDebug](icordebug-interface.md) antes de que se devuelva.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 `ppCordb` hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](icordebug-interface.md) .  
  
 E_INVALIDARG  
 `szDebuggeeVersion` o `ppCordb` es nulo.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 Componente que es necesario para que no se pueda encontrar la depuración de CLR. Esto significa que no se encontraron los archivos mscordbi.dll o mscordaccore.dll en el mismo directorio que CoreCLR.dll de destino.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede devolver una [interfaz ICorDebug](icordebug-interface.md).  
  
## <a name="remarks"></a>Notas  
 La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim. dll  
  
 **.NET Framework versiones:** 3,5 SP1
