---
title: CreateInstallReferenceEnum (Función)
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e35654b03f68a306329ef488289cfecd6f012484
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431579"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum (Función)
Obtiene un puntero a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instancia que representa una lista de referencias de una aplicación para el ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppRefEnum`  
 [out] El valor devuelto `IInstallReferenceEnum` puntero.  
  
 `pName`  
 [in] El [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) que identifica el ensamblado para el que se va a enumerar las referencias.  
  
 `dwFlags`  
 [in] Marcas que influyen en el comportamiento del enumerador.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** Fusion.dll y Mscorwks.dll. Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que la versión correcta de .NET Framework de destino.  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IInstallReferenceEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 [IAssemblyName (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
