---
title: Clase AssemblyAttributesGoHereSM (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
ms.openlocfilehash: 379ba20ebf675bec71e6e5f5bcfc0dc2fbd1f92c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446598"
---
# <a name="assemblyattributesgoheresm-class"></a>Clase AssemblyAttributesGoHereSM

ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.

## <a name="syntax"></a>Sintaxis

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a>Comentarios

Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado. Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales. Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.

Las referencias a este tipo indican atributos personalizados que están relacionados con la seguridad y que tienen diversos usos.

Estos tipos se marcan como "Internal" dentro del .NET Framework y se encuentran en el espacio de nombres <xref:System.Runtime.CompilerServices>.

## <a name="requirements"></a>Requisitos

mscorlib.dll

## <a name="see-also"></a>Vea también

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
