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
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="14e3e-102">Funciones auxiliares de Tlbexp (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="14e3e-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="14e3e-103">El [herramienta Exportador de la biblioteca de tipo](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos denominada TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="14e3e-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="14e3e-104">Este archivo DLL contiene dos funciones auxiliares y una interfaz que la herramienta exportador utiliza durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="14e3e-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14e3e-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="14e3e-105">In This Section</span></span>  
 [<span data-ttu-id="14e3e-106">GetTypeLibInfo (función)</span><span class="sxs-lookup"><span data-stu-id="14e3e-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="14e3e-107">Proporciona información de localización y el sistema operativo de una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="14e3e-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="14e3e-108">LoadTypeLibWithResolver (función)</span><span class="sxs-lookup"><span data-stu-id="14e3e-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="14e3e-109">Carga una biblioteca de tipos mediante el uso de una implementación de la [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) resolver cualquier referencia a las bibliotecas de tipos.</span><span class="sxs-lookup"><span data-stu-id="14e3e-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="14e3e-110">ITypeLibResolver (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14e3e-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="14e3e-111">Proporciona el [ResolveTypeLib (método)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="14e3e-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
