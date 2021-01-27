---
title: 'Cambio importante: Algunas propiedades de TableLayoutSettings producen una excepción InvalidEnumArgumentException.'
description: Obtenga información sobre el cambio importante de .NET 6.0 que provoca que algunas API de TableLayoutSettings produzcan una excepción InvalidEnumArgumentException para argumentos no válidos.
ms.date: 01/18/2021
ms.openlocfilehash: 8397952e4647347718f11597a100c5d764e7186b
ms.sourcegitcommit: f8cd3ef517ee177c99feed944824c27d208cc0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "98570252"
---
# <a name="selected-tablelayoutsettings-properties-throw-invalidenumargumentexception"></a><span data-ttu-id="20861-103">Ciertas propiedades de TableLayoutSettings producen la excepción InvalidEnumArgumentException</span><span class="sxs-lookup"><span data-stu-id="20861-103">Selected TableLayoutSettings properties throw InvalidEnumArgumentException</span></span>

<span data-ttu-id="20861-104">Ciertas propiedades de<xref:System.Windows.Forms.TableLayoutSettings> ahora producen una excepción <xref:System.ComponentModel.InvalidEnumArgumentException> si intenta asignar un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="20861-104">Selected <xref:System.Windows.Forms.TableLayoutSettings> properties now throw an <xref:System.ComponentModel.InvalidEnumArgumentException> if you attempt to assign an incorrect value.</span></span>

## <a name="change-description"></a><span data-ttu-id="20861-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="20861-105">Change description</span></span>

<span data-ttu-id="20861-106">En versiones anteriores de .NET, estas propiedades producían una excepción <xref:System.ArgumentOutOfRangeException> si intentaba asignar un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="20861-106">In previous .NET versions, these properties throw an <xref:System.ArgumentOutOfRangeException> if you attempt to assign an incorrect value.</span></span> <span data-ttu-id="20861-107">A partir de .NET 6.0, estas propiedades producen una excepción <xref:System.ComponentModel.InvalidEnumArgumentException> en estos casos.</span><span class="sxs-lookup"><span data-stu-id="20861-107">Starting in .NET 6.0, these properties throw an <xref:System.ComponentModel.InvalidEnumArgumentException> in such cases.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="20861-108">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="20861-108">Reason for change</span></span>

<span data-ttu-id="20861-109">La producción de la excepción <xref:System.ComponentModel.InvalidEnumArgumentException> es un funcionamiento acorde con la API de Windows Forms existente en situaciones similares.</span><span class="sxs-lookup"><span data-stu-id="20861-109">Throwing <xref:System.ComponentModel.InvalidEnumArgumentException> is in line with the existing Windows Forms API in similar situations.</span></span> <span data-ttu-id="20861-110">Esto también proporciona a los desarrolladores una mejor experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="20861-110">Throwing this exception also provides developers with a better debug experience.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="20861-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="20861-111">Version introduced</span></span>

<span data-ttu-id="20861-112">.NET 6.0</span><span class="sxs-lookup"><span data-stu-id="20861-112">.NET 6.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="20861-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="20861-113">Recommended action</span></span>

- <span data-ttu-id="20861-114">Actualice el código para evitar que se asignen valores incorrectos.</span><span class="sxs-lookup"><span data-stu-id="20861-114">Update the code to prevent assigning incorrect values.</span></span>
- <span data-ttu-id="20861-115">Si es necesario, controle una excepción <xref:System.ComponentModel.InvalidEnumArgumentException> al obtener acceso a estas API.</span><span class="sxs-lookup"><span data-stu-id="20861-115">If necessary, handle an <xref:System.ComponentModel.InvalidEnumArgumentException> when accessing these APIs.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="20861-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="20861-116">Affected APIs</span></span>

<span data-ttu-id="20861-117">En la tabla siguiente se enumeran las propiedades afectadas:</span><span class="sxs-lookup"><span data-stu-id="20861-117">The following table lists the affected properties:</span></span>

| <span data-ttu-id="20861-118">Propiedad</span><span class="sxs-lookup"><span data-stu-id="20861-118">Property</span></span> | <span data-ttu-id="20861-119">Versión de la modificación</span><span class="sxs-lookup"><span data-stu-id="20861-119">Version changed</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle?displayProperty=fullName> | <span data-ttu-id="20861-120">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="20861-120">Preview 1</span></span> |
| <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle?displayProperty=fullName> | <span data-ttu-id="20861-121">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="20861-121">Preview 1</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.TableLayoutPanel.CellBorderStyle`
- `P:System.Windows.Forms.TableLayoutPanel.GrowStyle`

### Category

Windows Forms

-->
