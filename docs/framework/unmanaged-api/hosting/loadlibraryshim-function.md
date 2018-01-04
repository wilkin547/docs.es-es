---
title: "LoadLibraryShim (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LoadLibraryShim
helpviewer_keywords: LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b8fe8413d0eff332e60508a083f03574e58d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim (Función)
Carga la versión especificada de un archivo DLL que se incluye en el paquete redistribuible de .NET Framework.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Use la [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szDllName`  
 [in] Una cadena terminada en cero que representa el nombre de la DLL que se va a cargar desde la biblioteca de .NET Framework.  
  
 `szVersion`  
 [in] Una cadena terminada en cero que representa la versión de la DLL que se va a cargar. Si `szVersion` es null, la versión seleccionada para la carga es la versión más reciente de la DLL especificada que es menor que la versión 4. Es decir, todas las versiones iguales o mayores que la versión 4 se omiten si `szVersion` es null, y si no está instalada ninguna versión menor que la versión 4, no puede cargar el archivo DLL. Esto sirve para asegurarse de esa instalación de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] no afecta a las aplicaciones existentes o componentes. Vea la entrada [SxS en proceso y el inicio rápido de migración](http://go.microsoft.com/fwlink/?LinkId=200329) en el blog del equipo CLR.  
  
 `pvReserved`  
 Reservado para un uso futuro.  
  
 `phModDll`  
 [out] Un puntero al identificador del módulo.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|CLR_E_SHIM_RUNTIMELOAD|Cargar `szDllName` requiere cargar common language runtime (CLR) y la versión necesaria de CLR no se puede cargar.|  
  
## <a name="remarks"></a>Comentarios  
 Esta función se usa para cargar archivos DLL que se incluyen en el paquete redistribuible de .NET Framework. No carga las DLL generadas por el usuario.  
  
> [!NOTE]
>  A partir de la versión 2.0 de .NET Framework, carga Fusion.dll hace que el CLR que se va a cargar. Esto es porque las funciones de Fusion.dll ahora son contenedores cuyas implementaciones se proporcionan con el tiempo de ejecución.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
