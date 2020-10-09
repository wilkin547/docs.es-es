---
title: Cambios importantes en la interoperabilidad
description: Enumera los cambios importantes de la interoperabilidad en .NET Core, .NET 5.0 y versiones posteriores.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438048"
---
# <a name="interop-breaking-changes"></a><span data-ttu-id="10974-103">Cambios importantes en la interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="10974-103">Interop breaking changes</span></span>

<span data-ttu-id="10974-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="10974-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="10974-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="10974-105">Breaking change</span></span> | <span data-ttu-id="10974-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="10974-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="10974-107">Excepción PlatformNotSupportedException al convertir un contenedor RCW en una interfaz de `InterfaceIsIInspectable`</span><span class="sxs-lookup"><span data-stu-id="10974-107">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | <span data-ttu-id="10974-108">5.0</span><span class="sxs-lookup"><span data-stu-id="10974-108">5.0</span></span> |
| [<span data-ttu-id="10974-109">Exclusión del sondeo del sufijo A/W en plataformas que no son de Windows</span><span class="sxs-lookup"><span data-stu-id="10974-109">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="10974-110">5.0</span><span class="sxs-lookup"><span data-stu-id="10974-110">5.0</span></span> |
| [<span data-ttu-id="10974-111">.NET deja de tener compatibilidad integrada con WinRT</span><span class="sxs-lookup"><span data-stu-id="10974-111">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="10974-112">5.0</span><span class="sxs-lookup"><span data-stu-id="10974-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="10974-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="10974-113">.NET 5.0</span></span>

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
