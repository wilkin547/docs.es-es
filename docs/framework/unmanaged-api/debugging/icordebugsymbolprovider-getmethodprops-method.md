---
title: ICorDebugSymbolProvider::GetMethodProps (método)
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784fcb10e9c0c3c6ff50c25d47bb4fb3fd5762ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161114"
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
  
## <a name="parameters"></a>Parámetros  
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
 Para obtener el tamaño necesario del método `signature` de matriz, establezca el `cbSignature` argumento en 0 y `signature` a **null**. Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetTypeProps (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [ICorDebugSymbolProvider (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
