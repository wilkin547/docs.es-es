---
title: PreBindAssemblyEx (Función)
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
ms.openlocfilehash: a729249f7b0681941a0b1a478dbe2c0d9d6cd01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723966"
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx (Función)

Obtiene el nombre para mostrar de la Directiva posterior de un ensamblado.  
  
 Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAppCtx`  
 de Identifica el contexto de la aplicación.  
  
 `pName`  
 de Identifica el nombre del ensamblado.  
  
 `pAsmParent`  
 de Identifica el ensamblado primario. Este parámetro se ignora.  
  
 `pwzRuntimeVersion`  
 de Identifica la versión del tiempo de ejecución.  
  
 `ppNamePostPolicy`  
 enuncia Contiene el nombre para mostrar de la Directiva posterior.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="remarks"></a>Comentarios  

 El `ppNamePostPolicy` parámetro de salida se establece solo si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH. En caso contrario, es null.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
