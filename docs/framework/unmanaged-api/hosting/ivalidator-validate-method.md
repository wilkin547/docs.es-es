---
title: "IValidator::Validate (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 722c6acc7e152a78ba28bc2730b2fdc7e0c45eb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate (Método)
Valida el archivo ejecutable portable (PE) especificado o el archivo de lenguaje intermedio (MSIL) de Microsoft.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `veh`  
 [in] Un puntero a un `IVEHandler` instancia que controla los errores de validación.  
  
 `pAppDomain`  
 [in] Un puntero al dominio de aplicación en el que se carga el archivo.  
  
 `ulFlags`  
 [in] Una combinación bit a bit de [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valores, que indican las validaciones que se deben realizar.  
  
 `ulMaxError`  
 [in] El número máximo de errores permitido antes de salir de la validación.  
  
 `token`  
 [in] No usado.  
  
 `fileName`  
 [in] Una cadena que especifica el nombre del archivo que se debe validar.  
  
 `pe`  
 [in] Un puntero al búfer de memoria en el que se almacena el archivo.  
  
 `ulSize`  
 [in] El tamaño, en bytes, del archivo que se debe validar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** IValidator.idl, IValidator.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
