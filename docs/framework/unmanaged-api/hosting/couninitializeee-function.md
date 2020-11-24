---
title: CoUninitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687852"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE (Función)

`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Comentarios  

 El motor de ejecución de Common Language Runtime no se puede descargar de un proceso. Para cerrar el motor de ejecución, llame a [CorExitProcess (](corexitprocess-function.md).  
  
## <a name="see-also"></a>Consulte también

- [CoInitializeEE (Función)](coinitializeee-function.md)
- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
