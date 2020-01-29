---
title: 'Función de activación: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734513"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Función Activate (referencia de la API no administrada de WPF)

Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.

Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.

## <a name="syntax"></a>Sintaxis

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Parameters

`pParameters`\
Puntero a los parámetros de activación de la ventana.

`ppInner`\
Puntero a la dirección de un búfer de un solo elemento que contiene un puntero a un objeto <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).

**DLL**

En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll

En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll

**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
