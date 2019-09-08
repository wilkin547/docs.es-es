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
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795393"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum (Función)
Obtiene un puntero a una instancia de [IInstallReferenceEnum (](iinstallreferenceenum-interface.md) que representa una lista de referencias de una aplicación al ensamblado especificado.  
  
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
 enuncia Puntero devuelto `IInstallReferenceEnum` .  
  
 `pName`  
 de La [IAssemblyName](iassemblyname-interface.md) que identifica el ensamblado para el que se van a enumerar las referencias.  
  
 `dwFlags`  
 de Marcas que influyen en el comportamiento del enumerador.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved`debe ser una referencia nula.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Biblioteca** Fusion. dll y mscorwks. dll. Use Fusion. dll en lugar de mscorwks. dll para asegurarse de que tiene como destino la versión correcta del .NET Framework.  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IInstallReferenceEnum (interfaz)](iinstallreferenceenum-interface.md)
- [IAssemblyName (interfaz)](iassemblyname-interface.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
