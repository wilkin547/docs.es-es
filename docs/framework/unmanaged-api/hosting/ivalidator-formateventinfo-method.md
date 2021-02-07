---
description: 'Más información acerca de: IValidator:: FormatEventInfo ((método)'
title: IValidator::FormatEventInfo (Método)
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 28ecf9ab2b14cd2fdd178a4ad9d8e218f7038a9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680166"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo (Método)

Obtiene el mensaje de error correspondiente al error de validación especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `hVECode`  
 de Valor HRESULT que se pasó al controlador de errores de validación.  
  
 `Context`  
 de `VEContext` Instancia de que contiene información de contexto sobre el error de validación.  
  
 `msg`  
 [in, out] Cadena que contiene el mensaje de error devuelto.  
  
 `ulMaxLength`  
 de La longitud máxima del mensaje de error.  
  
 `psa`  
 de Matriz segura que contiene los parámetros adicionales que describen el error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** IValidator. idl, IValidator. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
