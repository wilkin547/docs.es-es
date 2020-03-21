---
title: ICLRValidator::Validate (Método)
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178059"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate (Método)
Valida el ejecutable portátil (PE) o el lenguaje intermedio de Microsoft (MSIL) en el archivo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a>Parámetros  
 `veh`  
 [en] Puntero a `IVEHandler` una instancia que controla los errores de validación.  
  
 `ulAppDomainId`  
 [en] Identificador del <xref:System.AppDomain>archivo .  
  
 `ulFlags`  
 [en] Combinación de [valores ValidatorFlags,](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) que indica el tipo de validación que se debe realizar.  
  
 `ulMaxError`  
 [en] El número máximo de errores que se permiten antes de salir de la validación.  
  
 `token`  
 [in] Sin utilizar.  
  
 `fileName`  
 [en] El nombre del archivo que se va a validar.  
  
 `pe`  
 [en] Un puntero al búfer de archivos.  
  
 `ulSize`  
 [en] El tamaño, en bytes, del archivo que se va a validar.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Validate`regresó con éxito.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se adelantó la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no es el propietario de la cerradura.|  
|HOST_E_ABANDONED|Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.|  
|E_FAIL|Se ha producido un fallo catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** IValidator.idl, IValidator.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRValidator (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
