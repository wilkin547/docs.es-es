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
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616599"
---
# <a name="_corexemain-function"></a>_CorExeMain (Función)
Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Observaciones  
 El cargador llama a esta función en los procesos creados a partir de ensamblados ejecutables administrados. En el caso de los ensamblados DLL, el cargador llama a la función [_CorDllMain](cordllmain-function.md) en su lugar.  
  
 El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo de imagen.  
  
 En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorExeMain` función se llama indirectamente a través de una corrección en el cargador del sistema operativo. En todas las demás versiones de Windows, el cargador del sistema operativo lo llama directamente.  
  
 Para obtener más información, vea la sección Comentarios del tema [_CorValidateImage](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
