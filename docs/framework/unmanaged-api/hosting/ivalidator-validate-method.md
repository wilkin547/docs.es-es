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
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123282"
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate (Método)
Valida el archivo ejecutable portable (PE) o el archivo de lenguaje intermedio de Microsoft (MSIL) especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Puntero a una instancia de `IVEHandler` que controla los errores de validación.  
  
 `pAppDomain`  
 de Puntero al dominio de aplicación en el que se carga el archivo.  
  
 `ulFlags`  
 de Combinación bit a bit de valores de [ValidatorFlags (](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) , que indica las validaciones que se deben realizar.  
  
 `ulMaxError`  
 de Número máximo de errores que se permiten antes de salir de la validación.  
  
 `token`  
 de No se usa.  
  
 `fileName`  
 de Cadena que especifica el nombre del archivo que se va a validar.  
  
 `pe`  
 de Puntero al búfer de memoria en el que se almacena el archivo.  
  
 `ulSize`  
 de Tamaño, en bytes, del archivo que se va a validar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** IValidator. idl, IValidator. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
