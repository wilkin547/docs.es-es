---
description: 'Más información acerca de: Nukedownloadedcache ((función)'
title: NukeDownloadedCache (Función)
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 2239473b8e6e43a539b0507c8255d40f87e72043
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800037"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache (Función)

Elimina la memoria caché de descarga del Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h.  
  
## <a name="remarks"></a>Observaciones  

 La caché de descarga de CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan de una dirección URL para poder reutilizarlos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Biblioteca:** Fusion.dll y Mscorwks.dll. Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CreateHistoryReader (Función)](createhistoryreader-function.md)
- [GetHistoryFileDirectory (Función)](gethistoryfiledirectory-function.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
