---
description: 'Más información acerca de: Closeclrenumeration ((función)'
title: CloseCLREnumeration (Función)
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 7669332cc23b78afbb3bf597e7d208a5f707aae5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772775"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration (Función)

Cierra cualquier evento válido de Common Language Runtime (CLR) continue-startup ubicado en una matriz de identificadores devueltos por la [función enumerateclrs (](enumerateclrs-function.md)y libera la memoria para las matrices de rutas de acceso de identificador y de cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pHandleArray`  
 de Puntero a la matriz de identificadores de eventos devueltos por la [función enumerateclrs (](enumerateclrs-function.md).  
  
 `pStringArray`  
 de Puntero a la matriz de rutas de acceso de cadena CLR devuelta desde la [función enumerateclrs (](enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] DWORD que contiene el tamaño (longitud) de `pHandleArray` o `pStringArray` (son iguales).  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 Los identificadores abiertos por la [función enumerateclrs (](enumerateclrs-function.md) se cierran y se libera la memoria asignada para el identificador y las matrices de cadenas.  
  
 E_INVALIDARG  
 La longitud de `pHandleArray` no coincide con la longitud que se pasa en `dwArrayLength`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 La función no puede liberar la memoria para `pHandleArray` y `pStringArray`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim.dll  
  
 **.NET Framework versiones:** 3,5 SP1
