---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496118"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="c2308-101">En .NET Framework 4.6 no se usa una versión de 4.5.x.x al registrarse a sí mismo en el Registro</span><span class="sxs-lookup"><span data-stu-id="c2308-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

#### <a name="details"></a><span data-ttu-id="c2308-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c2308-102">Details</span></span>

<span data-ttu-id="c2308-103">Como se podría esperar, la clave de versión que se establece en el Registro (en <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) para .NET Framework 4.6 comienza con "4.6", no con "4.5".</span><span class="sxs-lookup"><span data-stu-id="c2308-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="c2308-104">Las aplicaciones que dependen de estas claves del Registro para saber qué versiones de .NET Framework están instaladas en un equipo se deben actualizar para entender que 4.6 es una nueva versión posible, y que es compatible con las versiones 4.5.x anteriores.</span><span class="sxs-lookup"><span data-stu-id="c2308-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c2308-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c2308-105">Suggestion</span></span>

<span data-ttu-id="c2308-106">Actualice las aplicaciones que sondean una instalación de .NET Framework 4.5 examinando las claves del Registro de 4.5 para que también acepten la versión 4.6.</span><span class="sxs-lookup"><span data-stu-id="c2308-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>

| <span data-ttu-id="c2308-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c2308-107">Name</span></span>    | <span data-ttu-id="c2308-108">Valor</span><span class="sxs-lookup"><span data-stu-id="c2308-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c2308-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c2308-109">Scope</span></span>   |<span data-ttu-id="c2308-110">Borde</span><span class="sxs-lookup"><span data-stu-id="c2308-110">Edge</span></span>|
|<span data-ttu-id="c2308-111">Versión</span><span class="sxs-lookup"><span data-stu-id="c2308-111">Version</span></span>|<span data-ttu-id="c2308-112">4.6</span><span class="sxs-lookup"><span data-stu-id="c2308-112">4.6</span></span>|
|<span data-ttu-id="c2308-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="c2308-113">Type</span></span>|<span data-ttu-id="c2308-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c2308-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c2308-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c2308-115">Affected APIs</span></span>

<span data-ttu-id="c2308-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="c2308-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
