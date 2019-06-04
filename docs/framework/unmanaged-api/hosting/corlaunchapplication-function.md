---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64527221e81569bf08a3cfd34a66681725755a55
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490536"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication (Función)
Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.  
  
 Esta función está desusada en .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in] Un valor de la [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeración que especifica el tipo de host que está iniciando la aplicación.  
  
 `pwzAppFullName`  
 [in] El nombre completo de la aplicación que se va a iniciar.  
  
 `dwManifestPaths`  
 [in] El número de rutas de acceso de manifiesto de la aplicación.  
  
 `ppwzManifestPaths`  
 [in] Una matriz de cadenas, cada uno de los cuales especifica una ruta de acceso para un manifiesto de la aplicación que se va a iniciar.  
  
 `dwActivationData`  
 [in] El número de elementos de datos de activación para la aplicación que se va a iniciar.  
  
 `ppwzActivationData`  
 [in] Una matriz de cadenas, cada uno de los cuales es un elemento de datos de activación para la aplicación que se va a iniciar.  
  
 `lpProcessInformation`  
 [out] Un puntero a información sobre el proceso en el que se ha cargado la aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
