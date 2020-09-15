---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614764"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a><span data-ttu-id="e3387-101">CspParameters.ParentWindowHandle espera ahora el valor HWND</span><span class="sxs-lookup"><span data-stu-id="e3387-101">CspParameters.ParentWindowHandle now expects HWND value</span></span>

#### <a name="details"></a><span data-ttu-id="e3387-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e3387-102">Details</span></span>

<span data-ttu-id="e3387-103">El valor <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, introducido en .NET Framework 2.0, permite que una aplicación registre un valor de identificador de ventana principal, de modo que cualquier interfaz de usuario necesaria para tener acceso a la clave (por ejemplo, una solicitud del PIN o un cuadro de diálogo de consentimiento) se abra como elemento secundario modal de la ventana especificada. A partir de las aplicaciones destinadas a .NET Framework 4.7, una aplicación de Windows Forms puede establecer la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> con código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3387-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> value, introduced in .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or consent dialog) opens as a modal child to the specified window.Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="e3387-104">En versiones anteriores de .NET Framework, se esperaba que el valor fuera un <xref:System.IntPtr?displayProperty=fullName> que representara una ubicación en memoria donde se encontraba el valor [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND).</span><span class="sxs-lookup"><span data-stu-id="e3387-104">In previous versions of the .NET Framework, the value was expected to be an <xref:System.IntPtr?displayProperty=fullName> representing a location in memory where the [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) value resided.</span></span> <span data-ttu-id="e3387-105">Establecer la propiedad en form.Handle no tenía ningún efecto en Windows 7 y versiones anteriores, pero en Windows 8 y versiones posteriores, da como resultado &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: El parámetro no es correcto&quot;.</span><span class="sxs-lookup"><span data-stu-id="e3387-105">Setting the property to form.Handle on Windows 7 and earlier versions had no effect, but on Windows 8 and later versions, it results in a &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e3387-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e3387-106">Suggestion</span></span>

<span data-ttu-id="e3387-107">Para las aplicaciones destinadas a .NET Framework 4.7 o versiones posteriores que quieran registrar una relación de ventana principal, se recomienda usar la forma simplificada:</span><span class="sxs-lookup"><span data-stu-id="e3387-107">Applications targeting .NET Framework 4.7 or higher wishing to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="e3387-108">Los usuarios que hayan identificado que el valor correcto para pasar era la dirección de una ubicación de memoria que contenía el valor `form.Handle`, pueden rechazar este cambio de comportamiento si establecen el modificador de AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` en `true`:</span><span class="sxs-lookup"><span data-stu-id="e3387-108">Users who had identified that the correct value to pass was the address of a memory location which held the value `form.Handle` can opt out of the behavior change by setting the AppContext switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="e3387-109">Configurando mediante programación los modificadores de compatibilidad en AppContext, como se explica [aquí](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="e3387-109">By programmatically setting compat switches on the AppContext, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="e3387-110">Agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="e3387-110">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

<span data-ttu-id="e3387-111">En cambio, los usuarios que quieran incluir el comportamiento nuevo en el entorno de ejecución de .NET Framework 4.7 cuando la aplicación se carga bajo versiones anteriores de .NET Framework, pueden establecer el modificador de AppContext en `false`.</span><span class="sxs-lookup"><span data-stu-id="e3387-111">Conversely, users who wish to opt in to the new behavior on the .NET Framework 4.7 runtime when the application loads under older .NET Framework versions can set the AppContext switch to `false`.</span></span>

| <span data-ttu-id="e3387-112">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e3387-112">Name</span></span>    | <span data-ttu-id="e3387-113">Valor</span><span class="sxs-lookup"><span data-stu-id="e3387-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e3387-114">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e3387-114">Scope</span></span>   | <span data-ttu-id="e3387-115">Secundaria</span><span class="sxs-lookup"><span data-stu-id="e3387-115">Minor</span></span>       |
| <span data-ttu-id="e3387-116">Versión</span><span class="sxs-lookup"><span data-stu-id="e3387-116">Version</span></span> | <span data-ttu-id="e3387-117">4.7</span><span class="sxs-lookup"><span data-stu-id="e3387-117">4.7</span></span>         |
| <span data-ttu-id="e3387-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="e3387-118">Type</span></span>    | <span data-ttu-id="e3387-119">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e3387-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e3387-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e3387-120">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
