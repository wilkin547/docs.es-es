---
title: CLRRuntimeHost (Coclase)
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616810"
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost (Coclase)
Proporciona interfaces para administrar la ejecución del código en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interfaz|Descripción|  
|---------------|-----------------|  
|[ICLRRuntimeHost (Interfaz)](iclrruntimehost-interface.md)|Proporciona métodos para controlar la ejecución de aplicaciones por parte del motor en tiempo de ejecución.|  
|[ICLRValidator (Interfaz)](iclrvalidator-interface.md)|Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Coclases para el hospedaje](hosting-coclasses.md)
