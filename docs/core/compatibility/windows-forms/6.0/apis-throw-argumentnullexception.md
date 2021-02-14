---
title: 'Cambio importante: Algunas API inician la excepción ArgumentNullException'
description: Obtenga información sobre el cambio importante en .NET 6.0 por el que algunas API validan argumentos y ahora inician una excepción ArgumentNullException.
ms.date: 01/29/2021
ms.openlocfilehash: f9d7dc8bb57ed8dc5b4ff41bda9b3bde7db7b880
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804155"
---
# <a name="some-apis-throw-argumentnullexception"></a><span data-ttu-id="cbd1d-103">Algunas API inician la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="cbd1d-103">Some APIs throw ArgumentNullException</span></span>

<span data-ttu-id="cbd1d-104">Algunas API ahora validan los parámetros de entrada e inician una excepción <xref:System.ArgumentNullException> donde anteriormente iniciaban una excepción <xref:System.NullReferenceException>, si se invocaban con argumentos de entrada `null`.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-104">Some APIs now validate input parameters and throw an <xref:System.ArgumentNullException> where previously they threw a <xref:System.NullReferenceException>, if invoked with `null` input arguments.</span></span>

## <a name="change-description"></a><span data-ttu-id="cbd1d-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="cbd1d-105">Change description</span></span>

<span data-ttu-id="cbd1d-106">En las versiones anteriores de .NET, las API afectadas iniciaban una excepción <xref:System.NullReferenceException> si la invocación se realizaba con un argumento que es `null`.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-106">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> if invoked with an argument that's `null`.</span></span>

<span data-ttu-id="cbd1d-107">A partir de .NET 6.0, las API afectadas iniciaban una excepción <xref:System.ArgumentNullException> si la invocación se realizaba con un argumento que es `null`.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-107">Starting in .NET 6.0, the affected APIs throw an <xref:System.ArgumentNullException> if invoked with an argument that's `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="cbd1d-108">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="cbd1d-108">Reason for change</span></span>

<span data-ttu-id="cbd1d-109">Iniciar <xref:System.ArgumentNullException> se ajusta al comportamiento del entorno de ejecución .NET.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-109">Throwing <xref:System.ArgumentNullException> conforms to .NET Runtime behavior.</span></span> <span data-ttu-id="cbd1d-110">Proporciona una mejor experiencia de depuración al comunicar claramente qué argumento produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-110">It provides a better debug experience by clearly communicating which argument caused the exception.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cbd1d-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cbd1d-111">Version introduced</span></span>

<span data-ttu-id="cbd1d-112">.NET 6.0</span><span class="sxs-lookup"><span data-stu-id="cbd1d-112">.NET 6.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="cbd1d-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cbd1d-113">Recommended action</span></span>

- <span data-ttu-id="cbd1d-114">Revise y, si es necesario, actualice el código para evitar pasar argumentos de entrada `null` a las API afectadas.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-114">Review and, if necessary, update your code to prevent passing `null` input arguments to the affected APIs.</span></span>
- <span data-ttu-id="cbd1d-115">Si el código controla <xref:System.NullReferenceException>, reemplace o agregue un controlador adicional para <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="cbd1d-115">If your code handles <xref:System.NullReferenceException>, replace or add an additional handler for <xref:System.ArgumentNullException>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="cbd1d-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cbd1d-116">Affected APIs</span></span>

<span data-ttu-id="cbd1d-117">En la tabla siguiente se enumeran las propiedades afectadas:</span><span class="sxs-lookup"><span data-stu-id="cbd1d-117">The following table lists the affected properties:</span></span>

| <span data-ttu-id="cbd1d-118">Propiedad</span><span class="sxs-lookup"><span data-stu-id="cbd1d-118">Property</span></span> | <span data-ttu-id="cbd1d-119">Versión de la modificación</span><span class="sxs-lookup"><span data-stu-id="cbd1d-119">Version changed</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName> | <span data-ttu-id="cbd1d-120">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="cbd1d-120">Preview 1</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->
