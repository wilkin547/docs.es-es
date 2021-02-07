---
description: 'Más información acerca de: CorLaunchApplication ((función)'
title: CorLaunchApplication (Función)
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
ms.openlocfilehash: 89f1f37ddde69fb5ecc24fd9dfd0d0c27d5fac40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716957"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication (Función)

Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwClickOnceHost`  
 de Un valor de la enumeración [HOST_TYPE](host-type-enumeration.md) que especifica el tipo de host que está iniciando la aplicación.  
  
 `pwzAppFullName`  
 de Nombre completo de la aplicación que se va a iniciar.  
  
 `dwManifestPaths`  
 de El número de rutas de acceso de manifiesto para la aplicación.  
  
 `ppwzManifestPaths`  
 de Matriz de cadenas, cada una de las cuales especifica una ruta de acceso a un manifiesto de la aplicación que se va a iniciar.  
  
 `dwActivationData`  
 de El número de elementos de datos de activación para la aplicación que se está iniciando.  
  
 `ppwzActivationData`  
 de Matriz de cadenas, cada una de las cuales es un elemento de datos de activación para la aplicación que se está iniciando.  
  
 `lpProcessInformation`  
 enuncia Puntero a información sobre el proceso en el que se ha cargado la aplicación.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
