---
description: 'Más información sobre: ICLRValidator:: Validate (método)'
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
ms.openlocfilehash: a188315d44021fc8bf40be9bb9aecac436351467
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636750"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate (Método)

Valida el ejecutable portable (PE) o el lenguaje intermedio de Microsoft (MSIL) en el archivo especificado.  
  
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
 de Puntero a una `IVEHandler` instancia de que controla los errores de validación.  
  
 `ulAppDomainId`  
 de Identificador del actual <xref:System.AppDomain> .  
  
 `ulFlags`  
 de Combinación de valores de [ValidatorFlags (](validatorflags-enumeration.md) , que indica el tipo de validación que se debe realizar.  
  
 `ulMaxError`  
 de Número máximo de errores que se permiten antes de salir de la validación.  
  
 `token`  
 [in] Sin utilizar.  
  
 `fileName`  
 de Nombre del archivo que se va a validar.  
  
 `pe`  
 de Puntero al búfer de archivos.  
  
 `ulSize`  
 de Tamaño, en bytes, del archivo que se va a validar.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Validate` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** IValidator. idl, IValidator. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRValidator (Interfaz)](iclrvalidator-interface.md)
