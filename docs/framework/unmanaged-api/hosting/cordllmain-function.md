---
description: 'Más información acerca de: _CorDllMain función'
title: _CorDllMain (Función)
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 442afae3a627eb684a86c02fbc6e546aa804b7a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717157"
---
# <a name="_cordllmain-function"></a>\_CorDllMain función)

Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `hInst`  
 de Identificador de instancia del módulo cargado.  
  
 `dwReason`  
 de Indica por qué se llama a la función de punto de entrada del archivo DLL. Este parámetro puede ser uno de los siguientes valores: DLL \_ PROCESS_ATTACH, \_ adjuntar subprocesos dll \_ , \_ adjuntar subprocesos dll \_ o \_ \_ desasociar proceso dll. Para obtener descripciones de estos valores, consulte la `DllMain` documentación del SDK de la plataforma.  
  
 `lpReserved`  
 [in] Sin utilizar.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve `true` un resultado correcto y `false` si se produce un error.  
  
## <a name="remarks"></a>Observaciones  

 El cargador del sistema operativo llama a esta función para los ensamblados DLL. En el caso de los ensamblados ejecutables, el cargador llama a la función [ \_ CorExeMain](corexemain-function.md) en su lugar.  
  
 El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.  
  
El `_CorDllMain` cargador del sistema operativo llama directamente a la función.
  
 Para obtener más información, vea la sección Comentarios en el tema [ \_ CorValidateImage](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
