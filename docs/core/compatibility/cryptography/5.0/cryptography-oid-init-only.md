---
title: 'Cambio importante: Cryptography.Oid es funcionalmente de solo inicialización'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde los establecedores de propiedad en la clase Cryptography.Oid ahora inician una excepción si intenta cambiar un valor.
ms.date: 08/16/2020
ms.openlocfilehash: a3b5a393e2a84f7c9a60c2a821ecfda9c6acd2e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760122"
---
# <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="c9157-103">System.Security.Cryptography.Oid es funcionalmente de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="c9157-103">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="c9157-104">La clase <xref:System.Security.Cryptography.Oid?displayProperty=fullName>, que se usa para representar valores de identificador de objeto ASN.1 y sus nombres "descriptivos", antes era completamente mutable.</span><span class="sxs-lookup"><span data-stu-id="c9157-104">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="c9157-105">Esta mutabilidad se solía pasar por alto o aparecía por sorpresa.</span><span class="sxs-lookup"><span data-stu-id="c9157-105">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="c9157-106">Los establecedores de propiedades ahora inician <xref:System.PlatformNotSupportedException> cuando se intenta cambiar el valor después de haberlo asignado.</span><span class="sxs-lookup"><span data-stu-id="c9157-106">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

## <a name="change-description"></a><span data-ttu-id="c9157-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c9157-107">Change description</span></span>

<span data-ttu-id="c9157-108">En versiones anteriores, los establecedores de propiedades en <xref:System.Security.Cryptography.Oid> se pueden usar para cambiar el valor de las propiedades <xref:System.Security.Cryptography.Oid.FriendlyName> y <xref:System.Security.Cryptography.Oid.Value>.</span><span class="sxs-lookup"><span data-stu-id="c9157-108">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="c9157-109">En .NET 5.0 y versiones posteriores, los establecedores de propiedad solo se pueden usar para inicializar el valor.</span><span class="sxs-lookup"><span data-stu-id="c9157-109">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="c9157-110">Una vez que la propiedad tiene un valor, ya sea desde un constructor o una llamada anterior al establecedor de propiedades, dicho establecedor de propiedades siempre inicia <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="c9157-110">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c9157-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c9157-111">Reason for change</span></span>

<span data-ttu-id="c9157-112">Este cambio permite reutilizar objetos <xref:System.Security.Cryptography.Oid> como parte de los valores devueltos en las API públicas para reducir los perfiles de asignación de objetos.</span><span class="sxs-lookup"><span data-stu-id="c9157-112">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="c9157-113">Evita la necesidad de crear copias "defensivas" temporales cuando se usan valores <xref:System.Security.Cryptography.Oid> como entradas.</span><span class="sxs-lookup"><span data-stu-id="c9157-113">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c9157-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c9157-114">Version introduced</span></span>

<span data-ttu-id="c9157-115">5.0</span><span class="sxs-lookup"><span data-stu-id="c9157-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c9157-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c9157-116">Recommended action</span></span>

<span data-ttu-id="c9157-117">Evite el uso de los establecedores de propiedades <xref:System.Security.Cryptography.Oid> que no sean para la inicialización de objetos.</span><span class="sxs-lookup"><span data-stu-id="c9157-117">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="c9157-118">Para representar un nuevo valor, use una nueva instancia en lugar de cambiar el valor en un objeto existente.</span><span class="sxs-lookup"><span data-stu-id="c9157-118">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c9157-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c9157-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

### Category

Cryptography

-->
