---
description: 'Más información acerca de: ICorDebugAppDomain:: GetModuleFromMetaDataInterface ((método)'
title: ICorDebugAppDomain::GetModuleFromMetaDataInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: 7b0c74bd04024f9f4bf26b5ee8abe18a3a7059e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754243"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a>ICorDebugAppDomain::GetModuleFromMetaDataInterface (Método)

Obtiene el módulo que corresponde a la interfaz de metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pIMetaData`  
 de Un puntero a un objeto que es una de las [interfaces de metadatos](../metadata/metadata-interfaces.md).  
  
 `ppModule`  
 enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo correspondiente a la interfaz de metadatos especificada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
