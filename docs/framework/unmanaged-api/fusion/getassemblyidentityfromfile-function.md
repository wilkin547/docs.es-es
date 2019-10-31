---
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
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134533"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile (Función)
Obtiene un puntero a un objeto `IUnknown` con el `IID` especificado en el ensamblado en la ruta de acceso de archivo especificada.  
  
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
 de `IID` de la interfaz que se va a devolver.  
  
 `ppIdentity`  
 enuncia Puntero de interfaz devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IUnknown](/cpp/atl/iunknown)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
