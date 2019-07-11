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
ms.openlocfilehash: da77d2eb848419c35e57ffacc8bf3d4580106fa5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764329"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum (Función)
Obtiene un puntero a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instancia que representa una lista de referencias de la aplicación para el ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppRefEnum`  
 [out] El valor devuelto `IInstallReferenceEnum` puntero.  
  
 `pName`  
 [in] El [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) que identifica el ensamblado que se va a enumerar las referencias.  
  
 `dwFlags`  
 [in] Marcas que influyen en el comportamiento del enumerador.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** El archivo Fusion.dll y Mscorwks.dll. Use el archivo Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IInstallReferenceEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [IAssemblyName (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
