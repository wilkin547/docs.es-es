---
title: ICorDebugSymbolProvider::GetMethodProps (método)
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: c9e73c4de7389405d9e4b643036709ff2dbb82e6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379566"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>ICorDebugSymbolProvider::GetMethodProps (método)
Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 [in] Tamaño de la matriz `signature`. Consulte la sección Comentarios.  
  
 `pcbSignature`  
 [out] Puntero al tamaño de la matriz `signature` devuelta.  
  
 `signature`  
 [out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.  
  
## <a name="remarks"></a>Observaciones  
 Para obtener el tamaño necesario de la matriz del método `signature` , establezca el `cbSignature` argumento en 0 y `signature` en **null**. Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetTypeProps](icordebugsymbolprovider-gettypeprops-method.md)
- [Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
