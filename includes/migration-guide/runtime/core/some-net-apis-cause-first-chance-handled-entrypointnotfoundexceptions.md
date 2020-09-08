---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496575"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="8ff74-101">Algunas API de .NET generan primeras excepciones EntryPointNotFoundExceptions (controladas)</span><span class="sxs-lookup"><span data-stu-id="8ff74-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="8ff74-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8ff74-102">Details</span></span>

<span data-ttu-id="8ff74-103">En .NET Framework 4.5, un pequeño número de métodos de .NET comenzaron a iniciar primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8ff74-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="8ff74-104">Estas primeras excepciones se controlaban dentro de .NET Framework, pero podían interrumpir la automatización de las pruebas que no las esperasen.</span><span class="sxs-lookup"><span data-stu-id="8ff74-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="8ff74-105">Estas mismas API interrumpen algunos escenarios de ApiVerifier con el elemento HighVersionLie habilitado.</span><span class="sxs-lookup"><span data-stu-id="8ff74-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8ff74-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8ff74-106">Suggestion</span></span>

<span data-ttu-id="8ff74-107">Este error puede evitarse actualizando a .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="8ff74-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="8ff74-108">Como alternativa, se puede actualizar la automatización de pruebas para que no se interrumpa con las primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8ff74-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="8ff74-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8ff74-109">Name</span></span>    | <span data-ttu-id="8ff74-110">Valor</span><span class="sxs-lookup"><span data-stu-id="8ff74-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ff74-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8ff74-111">Scope</span></span>   |<span data-ttu-id="8ff74-112">Borde</span><span class="sxs-lookup"><span data-stu-id="8ff74-112">Edge</span></span>|
|<span data-ttu-id="8ff74-113">Versión</span><span class="sxs-lookup"><span data-stu-id="8ff74-113">Version</span></span>|<span data-ttu-id="8ff74-114">4.5</span><span class="sxs-lookup"><span data-stu-id="8ff74-114">4.5</span></span>|
|<span data-ttu-id="8ff74-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="8ff74-115">Type</span></span>|<span data-ttu-id="8ff74-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8ff74-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8ff74-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8ff74-117">Affected APIs</span></span>

- <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)>

<!--

#### Affected APIs

- `M:System.Diagnostics.Debug.Assert(System.Boolean)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])`
- `M:System.Xml.Serialization.XmlSerializer.#ctor(System.Type)`

-->
