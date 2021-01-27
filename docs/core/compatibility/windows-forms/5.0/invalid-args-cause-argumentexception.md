---
title: 'Cambio importante: Los métodos de WinForms inician ahora la excepción ArgumentException'
description: Obtenga información sobre el cambio importante en .NET 5.0 por el que algunos métodos de Windows Forms ahora inician una excepción ArgumentException para los argumentos no válidos.
ms.date: 07/18/2020
ms.openlocfilehash: 892f4d16b80f3e42187480a7fcfb24e81868d07c
ms.sourcegitcommit: f8cd3ef517ee177c99feed944824c27d208cc0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "98570221"
---
# <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="83fd4-103">Los métodos de WinForms inician ahora la excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="83fd4-103">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="83fd4-104">Algunos métodos de Windows Forms inician ahora una excepción <xref:System.ArgumentException> en los argumentos no válidos, donde antes no lo hacían.</span><span class="sxs-lookup"><span data-stu-id="83fd4-104">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="83fd4-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="83fd4-105">Change description</span></span>

<span data-ttu-id="83fd4-106">Anteriormente, al pasar argumentos de un tipo inesperado o incorrecto a ciertos métodos de Windows Forms se originaba un estado indeterminado.</span><span class="sxs-lookup"><span data-stu-id="83fd4-106">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="83fd4-107">A partir de .NET 5.0, estos métodos inician una excepción <xref:System.ArgumentException> cuando se pasan argumentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="83fd4-107">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="83fd4-108">El inicio de una <xref:System.ArgumentException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="83fd4-108">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="83fd4-109">También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.</span><span class="sxs-lookup"><span data-stu-id="83fd4-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="83fd4-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="83fd4-110">Version introduced</span></span>

<span data-ttu-id="83fd4-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="83fd4-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="83fd4-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="83fd4-112">Recommended action</span></span>

- <span data-ttu-id="83fd4-113">Actualice el código para evitar pasar argumentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="83fd4-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="83fd4-114">Si es necesario, controle una excepción <xref:System.ArgumentException> al llamar al método.</span><span class="sxs-lookup"><span data-stu-id="83fd4-114">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="83fd4-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="83fd4-115">Affected APIs</span></span>

<span data-ttu-id="83fd4-116">En la tabla siguiente se enumeran los métodos y parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="83fd4-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="83fd4-117">Método</span><span class="sxs-lookup"><span data-stu-id="83fd4-117">Method</span></span> | <span data-ttu-id="83fd4-118">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="83fd4-118">Parameter name</span></span> | <span data-ttu-id="83fd4-119">Condición</span><span class="sxs-lookup"><span data-stu-id="83fd4-119">Condition</span></span> | <span data-ttu-id="83fd4-120">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="83fd4-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="83fd4-121">El argumento no es del tipo <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="83fd4-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="83fd4-122">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="83fd4-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="83fd4-123">El argumento es `null`, <xref:System.String.Empty?displayProperty=nameWithType> o un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="83fd4-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="83fd4-124">Versión preliminar 5</span><span class="sxs-lookup"><span data-stu-id="83fd4-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="83fd4-125">No se puede recuperar `InputLanguage` para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="83fd4-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="83fd4-126">Versión preliminar 7</span><span class="sxs-lookup"><span data-stu-id="83fd4-126">Preview 7</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
