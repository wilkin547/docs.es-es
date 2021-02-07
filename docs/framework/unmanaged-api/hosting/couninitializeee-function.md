---
description: 'Más información acerca de: CoUninitializeEE ((función)'
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
ms.openlocfilehash: e356135ea027bd52520eff9084ad2f7f09e1fe0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746170"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE (Función)

`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Observaciones  

 El motor de ejecución de Common Language Runtime no se puede descargar de un proceso. Para cerrar el motor de ejecución, llame a [CorExitProcess (](corexitprocess-function.md).  
  
## <a name="see-also"></a>Vea también

- [CoInitializeEE (Función)](coinitializeee-function.md)
- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
