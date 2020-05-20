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
ms.openlocfilehash: aae03b0dc76639c50f4615d41eef73990226b5f7
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442129"
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach (Método)
Realiza la Asociación automática del depurador invocado por el servidor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `guidPort`  
 de Siempre se establece en `GUID_NULL` .  
  
 `dwPid`  
 de IDENTIFICADOR de proceso, recuperado normalmente con la `GetCurrentProcessId` función.  
  
 `dwProgramType`  
 de Tipo de programa: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` o `AUTOATTACH_PROGRAM_UNKNOWN` .  
  
 `dwProgramId`  
 de IDENTIFICADOR de programa.  
  
 `pszSessionId`  
 de Cadena pasada por el verbo DEBUG.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** DbgAutoAttach. h  
  
## <a name="see-also"></a>Consulta también

- [IDebugAutoAttach (Interfaz)](idebugautoattach-interface.md)
