---
title: CoUninitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 8a8c2764398d737192190f91646d45f4edf3a0e4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616483"
---
# <a name="couninitializecor-function"></a>CoUninitializeCor (Función)
`CoUninitializeCor` está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>Observaciones  
 No se puede descargar el Common Language Runtime de un proceso. Para quitar completamente el Runtime de un proceso en ejecución, debe cerrar ese proceso.  
  
## <a name="see-also"></a>Consulta también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
