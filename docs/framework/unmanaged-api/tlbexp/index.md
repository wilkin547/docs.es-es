---
title: Funciones auxiliares de Tlbexp (Referencia de la API no administrada)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5d0a0b08be725a50442a3db9f9942bceea7cf8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funciones auxiliares de Tlbexp (Referencia de la API no administrada)
El [herramienta Exportador de la biblioteca de tipo](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos denominada TlbRef.dll. Este archivo DLL contiene dos funciones auxiliares y una interfaz que la herramienta exportador utiliza durante el proceso de conversión de ensamblado a biblioteca de tipos.  
  
## <a name="in-this-section"></a>En esta sección  
 [GetTypeLibInfo (función)](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Proporciona información de localización y el sistema operativo de una biblioteca de tipos.  
  
 [LoadTypeLibWithResolver (función)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Carga una biblioteca de tipos mediante el uso de una implementación de la [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) resolver cualquier referencia a las bibliotecas de tipos.  
  
 [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Proporciona el [ResolveTypeLib (método)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.
