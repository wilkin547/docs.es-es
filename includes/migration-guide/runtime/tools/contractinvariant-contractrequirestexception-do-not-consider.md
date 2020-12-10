---
ms.openlocfilehash: 639cd13978cc33bd7c4524a17e92d566404bbaea
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477397"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="6e126-101">Contract.Invariant o Contract.Requires\<TException> no consideran que String.IsNullOrEmpty sea puro</span><span class="sxs-lookup"><span data-stu-id="6e126-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="6e126-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e126-102">Details</span></span>

<span data-ttu-id="6e126-103">Para las aplicaciones que tienen como destino .NET Framework 4.6.1, si el contrato invariable para <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> o el contrato de condición previa para <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> llama al método <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>, el sistema de reescritura emite la advertencia del compilador CC1036: &quot;Se detectó la llamada al método "System.String.IsNullOrWhiteSpace(System.String)" sin [Pure] en el método.&quot; Se trata de una advertencia del compilador en lugar de un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="6e126-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhiteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6e126-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6e126-104">Suggestion</span></span>

<span data-ttu-id="6e126-105">Este comportamiento se solucionó en [Problema de GitHub #339](https://github.com/Microsoft/CodeContracts/issues/339).</span><span class="sxs-lookup"><span data-stu-id="6e126-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="6e126-106">Para eliminar esta advertencia, puede descargar y compilar una versión actualizada del código fuente para la herramienta Contratos de código desde [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="6e126-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="6e126-107">La información de descarga se encuentra en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="6e126-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="6e126-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e126-108">Name</span></span>    | <span data-ttu-id="6e126-109">Valor</span><span class="sxs-lookup"><span data-stu-id="6e126-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6e126-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6e126-110">Scope</span></span>   |<span data-ttu-id="6e126-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6e126-111">Minor</span></span>|
|<span data-ttu-id="6e126-112">Versión</span><span class="sxs-lookup"><span data-stu-id="6e126-112">Version</span></span>|<span data-ttu-id="6e126-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="6e126-113">4.6.1</span></span>|
|<span data-ttu-id="6e126-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e126-114">Type</span></span>|<span data-ttu-id="6e126-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6e126-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6e126-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6e126-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->
