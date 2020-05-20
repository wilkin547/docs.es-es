---
title: GetCORSystemDirectory (Función)
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 137b2e30916cb1934d4389c5668bfb7eb5066064
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617235"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory (Función)
Devuelve el directorio de instalación del Common Language Runtime (CLR) que se carga en el proceso. El directorio de instalación es completo, por ejemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705".  
  
 Esta función es desusada. Se sustituye por el método [ICLRRuntimeInfo:: GetRuntimeDirectory (](iclrruntimeinfo-getruntimedirectory-method.md) proporcionado en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Parámetros  
 `pbuffer`  
 enuncia Búfer en el que el tiempo de ejecución devuelve una cadena que contiene el nombre completo del directorio de instalación para el tiempo de ejecución que se carga en el proceso. Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.  
  
 `cchBuffer`  
 de Tamaño, en bytes, de `pbuffer` .  
  
 `dwLength`  
 enuncia Número de caracteres devueltos en `pbuffer` .  
  
## <a name="remarks"></a>Observaciones  
  
> [!CAUTION]
> No utilice esta función en los procesos que ejecutan la versión 4 de CLR. Si hay instalada una versión anterior de CLR en el equipo, esta función devuelve el directorio de instalación de esa versión.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
