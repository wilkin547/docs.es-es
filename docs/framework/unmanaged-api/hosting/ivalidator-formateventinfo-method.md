---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecbecec86d81357000679ab50e12f06d91c9f50d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765380"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo (Método)
Obtiene el mensaje de error correspondiente al error de validación especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in] El valor HRESULT que se pasó al controlador de errores de validación.  
  
 `Context`  
 [in] Un `VEContext` instancia que contiene información contextual sobre el error de validación.  
  
 `msg`  
 [in, out] Una cadena que contiene el mensaje de error devuelto.  
  
 `ulMaxLength`  
 [in] La longitud máxima del mensaje de error.  
  
 `psa`  
 [in] Una matriz segura que contiene parámetros adicionales que describe el error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: IValidator.idl, IValidator.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
