---
title: _CorExeMain (Función)
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: 8541e7761e2f8e1839d028fdaea3eb71307ba615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131201"
---
# <a name="_corexemain-function"></a>_CorExeMain (Función)
Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Comentarios  
 El cargador llama a esta función en los procesos creados a partir de ensamblados ejecutables administrados. En el caso de los ensamblados DLL, el cargador llama a la función [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) en su lugar.  
  
 El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo de imagen.  
  
 En Windows 98, Windows ME, Windows NT y Windows 2000, se llama indirectamente a la función `_CorExeMain` a través de una corrección en el cargador del sistema operativo. En todas las demás versiones de Windows, el cargador del sistema operativo lo llama directamente.  
  
 Para obtener más información, consulte la sección Comentarios del tema _ [corvalidateimage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
