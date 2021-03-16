---
title: 'Cambio importante: Al convertir RCW en `InterfaceIsIInspectable` se inicia una excepción'
description: Obtenga información sobre el cambio importante de interoperabilidad en .NET 5, en el que la conversión de un contenedor RCW a una interfaz `InterfaceIsIInspectable` inicia una excepción PlatformNotSupportedException.
ms.date: 09/13/2020
ms.openlocfilehash: 9f777ee9396f7822c9ff6bf5209021c07b8b618a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256639"
---
# <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a><span data-ttu-id="93261-103">Excepción PlatformNotSupportedException al convertir un contenedor RCW en una interfaz de `InterfaceIsIInspectable`</span><span class="sxs-lookup"><span data-stu-id="93261-103">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>

<span data-ttu-id="93261-104">Al convertir un contenedor RCW en una interfaz marcada como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, ahora se genera la excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="93261-104">Casting a runtime callable wrapper (RCW) to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> now throws a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="93261-105">Este cambio es una continuación de la [eliminación de la compatibilidad con WinRT de .NET](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="93261-105">This change is a follow up to the [removal of WinRT support from .NET](built-in-support-for-winrt-removed.md).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="93261-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="93261-106">Version introduced</span></span>

<span data-ttu-id="93261-107">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="93261-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="93261-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="93261-108">Change description</span></span>

<span data-ttu-id="93261-109">En las versiones de .NET anteriores a la versión preliminar 6 de .NET 5, la conversión de un contenedor RCW en una interfaz marcada como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> funcionaba según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="93261-109">In .NET versions prior to .NET 5 preview 6, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> works as expected.</span></span> <span data-ttu-id="93261-110">En las versiones preliminares 6 y 8 de NET 5 y RC1, se puede convertir correctamente un contenedor RCW en una interfaz de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>.</span><span class="sxs-lookup"><span data-stu-id="93261-110">In .NET 5 previews 6-8 and RC1, you can successfully cast an RCW to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface.</span></span> <span data-ttu-id="93261-111">Sin embargo, es posible que incurra en infracciones de acceso al ejecutar métodos en la interfaz, ya que la compatibilidad subyacente en el entorno de ejecución [se ha eliminado en la versión preliminar 6 de .NET 5](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="93261-111">However, you might get access violations when you execute methods on the interface, because the underlying support in the runtime [was removed in .NET 5 preview 6](built-in-support-for-winrt-removed.md).</span></span>

<span data-ttu-id="93261-112">En .NET 5 RC2 y versiones posteriores, al convertir un contenedor RCW en una interfaz marcada como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, se generaba una excepción <xref:System.PlatformNotSupportedException> durante la conversión.</span><span class="sxs-lookup"><span data-stu-id="93261-112">In .NET 5 RC2 and later versions, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> throws a <xref:System.PlatformNotSupportedException> at cast time.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="93261-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="93261-113">Reason for change</span></span>

<span data-ttu-id="93261-114">La compatibilidad con <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> [se eliminó en una versión preliminar anterior de .NET 5](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="93261-114">The support for <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> was [removed in a previous .NET 5 preview](built-in-support-for-winrt-removed.md).</span></span> <span data-ttu-id="93261-115">Sin embargo, la conversión en una interfaz de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> se pasó por alto debido a un error.</span><span class="sxs-lookup"><span data-stu-id="93261-115">However, casting to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface was accidentally overlooked.</span></span> <span data-ttu-id="93261-116">Como la compatibilidad subyacente en el entorno de ejecución ya no existe, al generar una excepción <xref:System.PlatformNotSupportedException>, se habilita una ruta de error gradual.</span><span class="sxs-lookup"><span data-stu-id="93261-116">Since the underlying support in the runtime no longer exists, throwing a <xref:System.PlatformNotSupportedException> enables a graceful failure path.</span></span> <span data-ttu-id="93261-117">Al generar una excepción, también se puede detectar con más facilidad que esta característica ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="93261-117">Throwing an exception also makes it more discoverable that this feature is no longer supported.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="93261-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="93261-118">Recommended action</span></span>

- <span data-ttu-id="93261-119">Si puede definir la interfaz en un archivo de metadatos del entorno de ejecución de Windows (WinMD), use la herramienta C#/WinRT.</span><span class="sxs-lookup"><span data-stu-id="93261-119">If you can define the interface in a Windows runtime metadata (WinMD) file, use the C#/WinRT tool instead.</span></span>

- <span data-ttu-id="93261-120">De lo contrario, marque la interfaz como <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> en lugar de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> y, después, agregue tres entradas ficticias al inicio de la interfaz para los métodos de <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>.</span><span class="sxs-lookup"><span data-stu-id="93261-120">Otherwise, mark the interface as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> instead of <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, and add three dummy entries to the start of the interface for the <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> methods.</span></span> <span data-ttu-id="93261-121">En el siguiente fragmento de código se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="93261-121">The following code snippet shows an example.</span></span>

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

## <a name="affected-apis"></a><span data-ttu-id="93261-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="93261-122">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

### Category

Interop

-->
