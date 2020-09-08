---
ms.openlocfilehash: 65fa5d8629ce8e426cf1623590a056e5cad0b91f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497670"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a><span data-ttu-id="98c38-101">La interoperabilidad de .NET se ejecutará ahora con QueryInterface para IAgileObject (una interfaz de WinRT)</span><span class="sxs-lookup"><span data-stu-id="98c38-101">.NET Interop will now QueryInterface for IAgileObject (a WinRT interface)</span></span>

#### <a name="details"></a><span data-ttu-id="98c38-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="98c38-102">Details</span></span>

<span data-ttu-id="98c38-103">Cuando se usa un evento de WinRT con un delegado de .NET, Windows se ejecutará con QI para IAgileObject a partir de .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="98c38-103">When using a WinRT event with a .NET delegate, Windows will QI for IAgileObject starting with the .NET Framework 4.8.</span></span>  <span data-ttu-id="98c38-104">En versiones anteriores de .NET Framework, el tiempo de ejecución producía un error en el QI y el evento no se podrá suscribir.</span><span class="sxs-lookup"><span data-stu-id="98c38-104">In previous versions of the .NET Framework, the runtime would fail that QI, and the event could not be subscribed.</span></span><ul><li><span data-ttu-id="98c38-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="98c38-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="98c38-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="98c38-106">Suggestion</span></span>

<span data-ttu-id="98c38-107">Si habilitar el QI para IAgileObject interrumpe la ejecución, puede deshabilitar este código estableciendo la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="98c38-107">If enabling the QI for IAgileObject breaks execution, you can disable this code by setting the following configuration.</span></span> <h4><span data-ttu-id="98c38-108">Método 1: Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="98c38-108">Method 1: Environment variable</span></span></h4> <span data-ttu-id="98c38-109">Establezca la siguiente variable de entorno: COMPLUS_DisableCCWSupportIAgileObject = 1Este método afecta a cualquier entorno que herede esta variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="98c38-109">Set the following environment variable:COMPLUS_DisableCCWSupportIAgileObject=1This method affects any environment that inherits this environment variable.</span></span> <span data-ttu-id="98c38-110">Podría tratarse simplemente de una sesión de consola única, o podría afectar a toda la máquina si establece la variable de entorno global.</span><span class="sxs-lookup"><span data-stu-id="98c38-110">This might be just a single console session, or it might affect the entire machine if you set the environment variable globally.</span></span> <span data-ttu-id="98c38-111">El nombre de la variable de entorno no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="98c38-111">The environment variable name is not case-sensitive.</span></span> <h4><span data-ttu-id="98c38-112">Método 2: Registro</span><span class="sxs-lookup"><span data-stu-id="98c38-112">Method 2: Registry</span></span></h4> <span data-ttu-id="98c38-113">Con el Editor del registro (regedit.exe), busque cualquiera de las siguientes subclaves:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkA continuación, agregue la siguiente: Nombre de valor: DisableCCWSupportIAgileObject Tipo: DWORD (32 bits) Valor (también denominado REG_WORD) Valor: 1Puede usar la herramienta de Windows REG.EXE para agregar este valor desde una línea de comandos o un entorno de scripting.</span><span class="sxs-lookup"><span data-stu-id="98c38-113">Using Registry Editor (regedit.exe), find either of the following subkeys:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkThen add the following:Value name: DisableCCWSupportIAgileObject Type: DWORD (32-bit) Value (also called REG_WORD) Value: 1You can use the Windows REG.EXE tool to add this value from a command-line or scripting environment.</span></span> <span data-ttu-id="98c38-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98c38-114">For example:</span></span><pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre><span data-ttu-id="98c38-115">En este caso, se usa <code>HKLM</code> en lugar de <code>HKEY_LOCAL_MACHINE</code>.</span><span class="sxs-lookup"><span data-stu-id="98c38-115">In this case, <code>HKLM</code> is used instead of <code>HKEY_LOCAL_MACHINE</code>.</span></span> <span data-ttu-id="98c38-116">Use <code>reg add /?</code> para ver la ayuda sobre esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="98c38-116">Use <code>reg add /?</code> to see help on this syntax.</span></span> <span data-ttu-id="98c38-117">El nombre del valor de registro no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="98c38-117">The registry value name is not case-sensitive.</span></span>

| <span data-ttu-id="98c38-118">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="98c38-118">Name</span></span>    | <span data-ttu-id="98c38-119">Valor</span><span class="sxs-lookup"><span data-stu-id="98c38-119">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="98c38-120">Ámbito</span><span class="sxs-lookup"><span data-stu-id="98c38-120">Scope</span></span>   |<span data-ttu-id="98c38-121">Borde</span><span class="sxs-lookup"><span data-stu-id="98c38-121">Edge</span></span>|
|<span data-ttu-id="98c38-122">Versión</span><span class="sxs-lookup"><span data-stu-id="98c38-122">Version</span></span>|<span data-ttu-id="98c38-123">4.8</span><span class="sxs-lookup"><span data-stu-id="98c38-123">4.8</span></span>|
|<span data-ttu-id="98c38-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="98c38-124">Type</span></span>|<span data-ttu-id="98c38-125">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="98c38-125">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="98c38-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="98c38-126">Affected APIs</span></span>

<span data-ttu-id="98c38-127">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="98c38-127">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
