---
title: Funciones del asistente de Tlbexp (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967705"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="c6aba-102">Funciones del asistente de Tlbexp (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c6aba-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="c6aba-103">La [herramienta Exportador de la biblioteca de tipos](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos (DLL) denominada TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="c6aba-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="c6aba-104">Esta DLL contiene dos funciones auxiliares y una interfaz que usa la herramienta de exportación durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c6aba-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6aba-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c6aba-105">In This Section</span></span>  
 [<span data-ttu-id="c6aba-106">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c6aba-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="c6aba-107">Proporciona información de localización y sistema operativo para una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c6aba-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="c6aba-108">LoadTypeLibWithResolver (Función)</span><span class="sxs-lookup"><span data-stu-id="c6aba-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="c6aba-109">Carga una biblioteca de tipos mediante el uso de una implementación de la [interfaz ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) para resolver cualquier biblioteca de tipos a la que se haga referencia.</span><span class="sxs-lookup"><span data-stu-id="c6aba-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="c6aba-110">ITypeLibResolver (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6aba-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="c6aba-111">Proporciona el [método ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c6aba-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
