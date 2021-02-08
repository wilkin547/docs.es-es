---
description: 'Más información acerca de: interfaz IInstallReferenceEnum ('
title: IInstallReferenceEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: 496bd508b95b51cb23949f32f8390c7cb733b37e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800113"
---
# <a name="iinstallreferenceenum-interface"></a>IInstallReferenceEnum (Interfaz)

Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetNextInstallReferenceItem](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|Obtiene un puntero al siguiente `IInstallReferenceItem` contenido en este `IInstallReferenceEnum` .|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IInstallReferenceItem (Interfaz)](iinstallreferenceitem-interface.md)
