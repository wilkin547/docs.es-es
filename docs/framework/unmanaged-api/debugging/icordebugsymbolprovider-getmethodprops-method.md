---
title: "ICorDebugSymbolProvider::GetMethodProps (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 58406f3f47e5d6eabd55420dc57148dc7f264726
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>ICorDebugSymbolProvider::GetMethodProps (método)
Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `codeRVA`  
 [in] Dirección virtual relativa del método acerca de qué información se va a recuperar.  
  
 `pMethodToken`  
 [out] Puntero al token de metadatos del método.  
  
 `pcGenericParams`  
 [out] Puntero al número de parámetros genéricos asociados a este método.  
  
 `cbSignature`  
 [in] Tamaño de la matriz `signature`. Vea la sección Comentarios.  
  
 `pcbSignature`  
 [out] Puntero al tamaño de la matriz `signature` devuelta.  
  
 `signature`  
 [out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.  
  
## <a name="remarks"></a>Comentarios  
 Para obtener el tamaño necesario del método `signature` de matriz, establezca la `cbSignature` argumento pasado a 0 y `signature` a **null**. Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [GetTypeProps (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)  
 [Interfaz ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
