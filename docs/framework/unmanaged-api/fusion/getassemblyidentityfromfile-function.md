---
description: 'Más información acerca de: Getassemblyidentityfromfile ((función)'
title: GetAssemblyIdentityFromFile (Función)
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 8832e03182a5652c938404c99115fa8059439d1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761045"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile (Función)

Obtiene un puntero a un `IUnknown` objeto con el especificado `IID` en el ensamblado en la ruta de acceso de archivo especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a>Parámetros  

 `pwzFilePath`  
 de Ruta de acceso válida al ensamblado solicitado.  
  
 `riid`  
 de `IID` De la interfaz que se va a devolver.  
  
 `ppIdentity`  
 enuncia Puntero de interfaz devuelto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IUnknown](/cpp/atl/iunknown)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
