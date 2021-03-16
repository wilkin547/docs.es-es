---
title: 'Cambio importante: Nombres de parámetro modificados en RC2'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde se han cambiado algunos nombres de parámetro de ensamblado de referencia de las versiones preliminares y candidatas para lanzamiento de .NET 5.0.
ms.date: 11/01/2020
ms.openlocfilehash: caca9055bda50174b40d5675c6d34679df61deba
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257198"
---
# <a name="parameter-names-changed-in-rc2"></a><span data-ttu-id="5e396-103">Nombres de parámetro modificados en RC2</span><span class="sxs-lookup"><span data-stu-id="5e396-103">Parameter names changed in RC2</span></span>

<span data-ttu-id="5e396-104">Se han cambiado algunos nombres de parámetros de ensamblado de referencia para coincidir con los nombres de parámetro de los ensamblados de implementación.</span><span class="sxs-lookup"><span data-stu-id="5e396-104">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

## <a name="change-description"></a><span data-ttu-id="5e396-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5e396-105">Change description</span></span>

<span data-ttu-id="5e396-106">En versiones anteriores de .NET 5 Preview y RC, algunos nombres de parámetros de [ensamblado de referencia](../../../../standard/assembly/reference-assemblies.md) son diferentes de sus parámetros correspondientes en el ensamblado de implementación.</span><span class="sxs-lookup"><span data-stu-id="5e396-106">In previous .NET 5 preview and RC versions, some [reference assembly](../../../../standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="5e396-107">Esto puede producir problemas al usar argumentos con nombre y reflexión.</span><span class="sxs-lookup"><span data-stu-id="5e396-107">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="5e396-108">En .NET 5 RC2, estos nombres de parámetros no coincidentes se han actualizado en los ensamblados de referencia para que coincidan exactamente con los nombres de parámetro correspondientes en los ensamblados de implementación.</span><span class="sxs-lookup"><span data-stu-id="5e396-108">In .NET 5 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="5e396-109">En esta tabla se muestran las API y los nombres de los parámetros que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="5e396-109">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="5e396-110">API</span><span class="sxs-lookup"><span data-stu-id="5e396-110">API</span></span> | <span data-ttu-id="5e396-111">Nombre del parámetro antiguo</span><span class="sxs-lookup"><span data-stu-id="5e396-111">Old parameter name</span></span> | <span data-ttu-id="5e396-112">Nombre del parámetro nuevo</span><span class="sxs-lookup"><span data-stu-id="5e396-112">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a><span data-ttu-id="5e396-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5e396-113">Reason for change</span></span>

<span data-ttu-id="5e396-114">Los nombres de los parámetros se han cambiado por coherencia y para evitar errores al usar argumentos con nombre y reflexión.</span><span class="sxs-lookup"><span data-stu-id="5e396-114">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5e396-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5e396-115">Version introduced</span></span>

<span data-ttu-id="5e396-116">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="5e396-116">5.0 RC2</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5e396-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5e396-117">Recommended action</span></span>

<span data-ttu-id="5e396-118">Si se produce un error del compilador debido a un cambio de nombre de un parámetro, actualice el nombre del parámetro en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="5e396-118">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5e396-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5e396-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
