---
title: ICLRRuntimeHost (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: 72caac0aafe7f9c5919057a6ad2565258aec6a50
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504087"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost (Interfaz)
Proporciona una funcionalidad similar a la de la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) proporcionada en el .NET Framework versión 1, con los siguientes cambios:  
  
- La adición del método [SetHostControl](iclrruntimehost-sethostcontrol-method.md) para establecer la interfaz de control host.  
  
- La omisión de algunos métodos proporcionados por `ICorRuntimeHost` .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ExecuteApplication](iclrruntimehost-executeapplication-method.md)|Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo.|  
|[Método ExecuteInAppDomain](iclrruntimehost-executeinappdomain-method.md)|Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.|  
|[Método ExecuteInDefaultAppDomain](iclrruntimehost-executeindefaultappdomain-method.md)|Invoca el método especificado del tipo especificado en el ensamblado especificado.|  
|[Método GetCLRControl](iclrruntimehost-getclrcontrol-method.md)|Obtiene un puntero de interfaz de tipo [ICLRControl](iclrcontrol-interface.md) que los hosts pueden utilizar para personalizar los aspectos del Common Language Runtime (CLR).|  
|[Método GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md)|Obtiene el identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.|  
|[Método SetHostControl](iclrruntimehost-sethostcontrol-method.md)|Establece la interfaz de control host. Debe llamar a `SetHostControl` antes de llamar a `Start` .|  
|[Start (método)](iclrruntimehost-start-method.md)|Inicializa CLR en un proceso.|  
|[Stop (Método)](iclrruntimehost-stop-method.md)|Detiene la ejecución del código en tiempo de ejecución.|  
|[Método UnloadAppDomain](iclrruntimehost-unloadappdomain-method.md)|Descarga el <xref:System.AppDomain> que corresponde al identificador numérico especificado.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la .NET Framework 4, use la interfaz [ICLRMetaHost](iclrmetahost-interface.md) para obtener un puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) y, a continuación, llame al método [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) para obtener un puntero a `ICLRRuntimeHost` . En versiones anteriores del .NET Framework, el host obtiene un puntero a una instancia llamando a `ICLRRuntimeHost` [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md). Para proporcionar implementaciones de cualquiera de las tecnologías que se proporcionan en la .NET Framework versión 2,0, debe utilizar `ICLRRuntimeHost` en lugar de `ICorRuntimeHost` .  
  
> [!IMPORTANT]
> No llame al método [Start](iclrruntimehost-start-method.md) antes de llamar al método [ExecuteApplication (](iclrruntimehost-executeapplication-method.md) para activar una aplicación basada en manifiesto. Si `Start` se llama primero al método, `ExecuteApplication` se producirá un error en la llamada al método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [CorBindToCurrentRuntime (Función)](corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [CLRRuntimeHost (Coclase)](clrruntimehost-coclass.md)
