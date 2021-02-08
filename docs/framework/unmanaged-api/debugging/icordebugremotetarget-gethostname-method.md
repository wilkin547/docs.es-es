---
description: 'Más información sobre: ICorDebugRemoteTarget:: GetHostName ((método)'
title: ICorDebugRemoteTarget::GetHostName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: a24f34dd638c7031211c2185cd761af0aa24105e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803531"
---
# <a name="icordebugremotetargetgethostname-method"></a>ICorDebugRemoteTarget::GetHostName (Método)

Devuelve el nombre de dominio completo o la dirección IPv4 del equipo de destino de depuración remota. IPV6 no se admite en este momento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchHostName`  
 [in] Tamaño, en caracteres, del búfer de `szHostName`. Si este parámetros es 0 (cero), `szHostName` debe ser NULL.  
  
 `pcchHostName`  
 [out] Número de caracteres, incluido un terminador nulo, en el nombre de host o dirección IP. Este parámetro puede ser NULL.  
  
 `szHostName`  
 [out] Búfer que contiene el nombre de host o la dirección IP.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 El nombre de host o la dirección IP se devolvieron correctamente.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede devolver el nombre de host o la dirección IP.  
  
## <a name="remarks"></a>Observaciones  

 Este método lo implementa el programador del depurador. Debe seguir el paradigma de llamada múltiple: en la primera llamada, el llamador pasa null a `cchHostName` y `szHostName` , y `pcchHostName` devuelve el tamaño del búfer necesario. En la segunda llamada, el tamaño devuelto previamente se pasa en `cchHostName`, y un búfer del tamaño adecuado se pasa en `szHostName`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 3,5 SP1  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRemoteTarget (Interfaz)](icordebugremotetarget-interface.md)
- [ICorDebug (Interfaz)](icordebug-interface.md)
