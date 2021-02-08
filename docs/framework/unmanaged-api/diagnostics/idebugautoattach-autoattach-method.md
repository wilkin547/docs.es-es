---
description: 'Más información sobre: IDebugAutoAttach (:: AutoAttach (método)'
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
ms.openlocfilehash: 8abd35b1d94fc074d4dafe424c52c274b1de1541
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800362"
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
  
## <a name="see-also"></a>Vea también

- [IDebugAutoAttach (Interfaz)](idebugautoattach-interface.md)
