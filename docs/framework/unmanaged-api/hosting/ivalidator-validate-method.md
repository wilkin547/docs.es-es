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
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699149"
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
 de Puntero a una `IVEHandler` instancia de que controla los errores de validación.  
  
 `pAppDomain`  
 de Puntero al dominio de aplicación en el que se carga el archivo.  
  
 `ulFlags`  
 de Combinación bit a bit de valores de [ValidatorFlags (](validatorflags-enumeration.md) , que indica las validaciones que se deben realizar.  
  
 `ulMaxError`  
 de Número máximo de errores que se permiten antes de salir de la validación.  
  
 `token`  
 [in] No se utiliza.  
  
 `fileName`  
 de Cadena que especifica el nombre del archivo que se va a validar.  
  
 `pe`  
 de Puntero al búfer de memoria en el que se almacena el archivo.  
  
 `ulSize`  
 de Tamaño, en bytes, del archivo que se va a validar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** IValidator. idl, IValidator. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
