---
title: IValidator::Validate (Método)
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fba06360a0c31e0a7fa3e61de9793bad14650fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765302"
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
  
## <a name="parameters"></a>Parámetros  
 `veh`  
 [in] Un puntero a un `IVEHandler` instancia que controla los errores de validación.  
  
 `pAppDomain`  
 [in] Un puntero al dominio de aplicación en el que se carga el archivo.  
  
 `ulFlags`  
 [in] Una combinación bit a bit de [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valores, que indica las validaciones que se deben realizar.  
  
 `ulMaxError`  
 [in] El número máximo de errores permitido antes de salir de la validación.  
  
 `token`  
 [in] No se utiliza.  
  
 `fileName`  
 [in] Una cadena que especifica el nombre del archivo que se va a validar.  
  
 `pe`  
 [in] Un puntero al búfer de memoria donde se almacena el archivo.  
  
 `ulSize`  
 [in] El tamaño, en bytes, del archivo que se va a validar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: IValidator.idl, IValidator.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
