---
title: Funciones del asistente de Tlbexp (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: cbde2af9c8a03e6c41f571120027030713f1b8d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73104125"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="c77fd-102">Funciones del asistente de Tlbexp (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c77fd-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="c77fd-103">La [herramienta Exportador de la biblioteca de tipos](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos (DLL) denominada TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="c77fd-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="c77fd-104">Esta DLL contiene dos funciones auxiliares y una interfaz que usa la herramienta de exportación durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c77fd-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c77fd-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c77fd-105">In This Section</span></span>  
 [<span data-ttu-id="c77fd-106">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c77fd-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="c77fd-107">Proporciona información de localización y sistema operativo para una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c77fd-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="c77fd-108">LoadTypeLibWithResolver (Función)</span><span class="sxs-lookup"><span data-stu-id="c77fd-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="c77fd-109">Carga una biblioteca de tipos mediante el uso de una implementación de la [interfaz ITypeLibResolver](itypelibresolver-interface.md) para resolver cualquier biblioteca de tipos a la que se haga referencia.</span><span class="sxs-lookup"><span data-stu-id="c77fd-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="c77fd-110">ITypeLibResolver (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c77fd-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="c77fd-111">Proporciona el [método ResolveTypeLib](resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c77fd-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
