---
title: ICorRuntimeHost::MapFile (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
ms.openlocfilehash: 3b1a0cd9a1dfba6f33a20416f2a10c967f871a06
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762674"
---
# <a name="icorruntimehostmapfile-method"></a>ICorRuntimeHost::MapFile (Método)
Asigna el archivo especificado a la memoria. Este método está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hFile`  
 de Identificador del archivo que se va a asignar.  
  
 `hMapAddress`  
 enuncia Dirección de memoria de inicio en la que se va a empezar a asignar el archivo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versión de .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Consulte también:

- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
