---
description: 'Más información acerca de: Callfunctionshim ((función)'
title: CallFunctionShim (Función)
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: 7ddd16a06005011adcf41190929fd62f4132f14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799959"
---
# <a name="callfunctionshim-function"></a>CallFunctionShim (Función)

Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szDllName`  
 de Nombre de la biblioteca que contiene la función.  
  
 `szFunctionName`  
 de Nombre de la función.  
  
 `lpvArgument1`  
 de Primer argumento que se va a pasar a la función.  
  
 `lpvArgument2`  
 de Segundo argumento que se va a pasar a la función.  
  
 `szVersion`  
 de Versión de la biblioteca que contiene la función.  
  
 `pvReserved`  
 [in] Reservado para uso futuro. Pase cero en este parámetro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
