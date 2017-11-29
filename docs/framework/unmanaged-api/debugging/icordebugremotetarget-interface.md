---
title: ICorDebugRemoteTarget (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget
helpviewer_keywords: ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38357072b3a6e8e8a326a16600b2d7ed56cdcb2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget (Interfaz)
Proporciona métodos que permiten a los desarrolladores depurar aplicaciones basadas en Silverlight en el entorno de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Icordebugremotetarget:: gethostname (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|Devuelve el nombre de host o la dirección IP de un equipo remoto.|  
  
## <a name="remarks"></a>Comentarios  
 No se admite la depuración en modo mixto (es decir, código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas que no sean x86 (como IA-64 y AMD64).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl  
  
 **Biblioteca:** : CorGuids.lib  
  
 **Versiones de .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugRemote (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
