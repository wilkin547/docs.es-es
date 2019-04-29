---
title: Activate (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777174"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Activate (función) (referencia de API no administrada de WPF)

Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.

Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.

## <a name="syntax"></a>Sintaxis

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Parámetros

`pParameters`\
Un puntero a los parámetros de activación de la ventana.

`ppInner`\
Un puntero a la dirección de un búfer único elemento que contiene un puntero a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> objeto.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).

**ARCHIVO DLL:**

En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll

En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll

**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
