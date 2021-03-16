---
title: 'Cambio importante: IntPtr y UIntPtr implementan IFormattable'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde IntPtr y UIntPtr implementan ahora IFormattable.
ms.date: 11/01/2020
ms.openlocfilehash: adfb68807d5fa5f0c750fb41ef75951f63a4b2d5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257445"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="fb873-103">IntPtr y UIntPtr implementan IFormattable</span><span class="sxs-lookup"><span data-stu-id="fb873-103">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="fb873-104"><xref:System.IntPtr> y <xref:System.UIntPtr> ahora implementan <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="fb873-104"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="fb873-105">Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="fb873-105">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

## <a name="change-description"></a><span data-ttu-id="fb873-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="fb873-106">Change description</span></span>

<span data-ttu-id="fb873-107">En versiones anteriores de .NET, <xref:System.IntPtr> y <xref:System.UIntPtr> no implementan <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="fb873-107">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="fb873-108">Las funciones que comprueban <xref:System.IFormattable> pueden revertir simplemente a llamar a <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> o <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, lo que significa que no se respetan los especificadores de formato ni las referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="fb873-108">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="fb873-109">En .NET 5 y versiones posteriores, <xref:System.IntPtr> y <xref:System.UIntPtr> implementan <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="fb873-109">In .NET 5 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="fb873-110">Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="fb873-110">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="fb873-111">Este cambio afecta a escenarios como cadenas interpoladas y <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, entre otros.</span><span class="sxs-lookup"><span data-stu-id="fb873-111">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="fb873-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="fb873-112">Reason for change</span></span>

<span data-ttu-id="fb873-113"><xref:System.IntPtr> y <xref:System.UIntPtr> ahora tienen compatibilidad de lenguaje en C# mediante las palabras clave `nint` y `nuint`.</span><span class="sxs-lookup"><span data-stu-id="fb873-113"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="fb873-114">Los tipos de respaldo se han actualizado para proporcionar paridad cercana (siempre que sea posible) con funcionalidad expuesta por otros tipos primitivos, como <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb873-114">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="fb873-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fb873-115">Version introduced</span></span>

<span data-ttu-id="fb873-116">5.0</span><span class="sxs-lookup"><span data-stu-id="fb873-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="fb873-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="fb873-117">Recommended action</span></span>

<span data-ttu-id="fb873-118">Si no quiere que se use un especificador de formato o una referencia cultural personalizada al mostrar valores de estos tipos, puede llamar a las sobrecargas <xref:System.IntPtr.ToString?displayProperty=nameWithType> y <xref:System.UIntPtr.ToString?displayProperty=nameWithType> de `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="fb873-118">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="fb873-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fb873-119">Affected APIs</span></span>

<span data-ttu-id="fb873-120">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="fb873-120">Not detectable via API analysis.</span></span>

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
