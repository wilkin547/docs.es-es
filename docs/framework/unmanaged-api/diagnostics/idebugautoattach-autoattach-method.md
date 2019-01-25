---
title: IDebugAutoAttach::AutoAttach (Método)
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b45b5e1a7589329b788160df3ac4493efa48197
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663523"
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach (Método)
Realiza automática del depurador invocado por el servidor de adjuntar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `guidPort`  
 [in] Siempre se establece en `GUID_NULL`.  
  
 `dwPid`  
 [in] Identificador del proceso, normalmente se recuperan con el `GetCurrentProcessId` función.  
  
 `dwProgramType`  
 [in] Tipo de programa: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, o `AUTOATTACH_PROGRAM_UNKNOWN`.  
  
 `dwProgramId`  
 [in] Identificador de programa.  
  
 `pszSessionId`  
 [in] Cadena pasada por el verbo debug.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: DbgAutoAttach.h  
  
## <a name="see-also"></a>Vea también
- [IDebugAutoAttach (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
