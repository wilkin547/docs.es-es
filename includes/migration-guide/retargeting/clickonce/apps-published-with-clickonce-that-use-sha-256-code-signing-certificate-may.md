---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615747"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="ff7a6-101">Puede producirse un error en las aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA-256 en Windows 2003</span><span class="sxs-lookup"><span data-stu-id="ff7a6-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

#### <a name="details"></a><span data-ttu-id="ff7a6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ff7a6-102">Details</span></span>

<span data-ttu-id="ff7a6-103">El archivo ejecutable está firmado con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="ff7a6-104">Antes se firmaba con SHA1, independientemente de si el certificado de firma de código era SHA-1 o SHA-256.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="ff7a6-105">Esto se aplica a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff7a6-105">This applies to:</span></span>

- <span data-ttu-id="ff7a6-106">Todas las aplicaciones compiladas con Visual Studio 2012 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-106">All applications built with Visual Studio 2012 or later.</span></span>
- <span data-ttu-id="ff7a6-107">Aplicaciones compiladas con Visual Studio 2010 o versiones anteriores en sistemas con .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span>
<span data-ttu-id="ff7a6-108">Además, si está presente .NET Framework 4.5 o versiones posteriores, el manifiesto de ClickOnce también está firmado con SHA-256 para certificados SHA-256, independientemente de la versión de .NET Framework con la que se compiló.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ff7a6-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ff7a6-109">Suggestion</span></span>

<span data-ttu-id="ff7a6-110">El cambio en la firma del ejecutable ClickOnce solo afecta a los sistemas Windows Server 2003; necesitan que KB 938397 esté instalado.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.</span></span> <span data-ttu-id="ff7a6-111">El cambio al firmar el manifiesto con SHA-256, incluso cuando una aplicación tiene como destino .NET Framework 4.0 o versiones anteriores, introduce una dependencia de tiempo de ejecución en .NET Framework 4.5 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-111">The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>

| <span data-ttu-id="ff7a6-112">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ff7a6-112">Name</span></span>    | <span data-ttu-id="ff7a6-113">Valor</span><span class="sxs-lookup"><span data-stu-id="ff7a6-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ff7a6-114">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ff7a6-114">Scope</span></span>   | <span data-ttu-id="ff7a6-115">Borde</span><span class="sxs-lookup"><span data-stu-id="ff7a6-115">Edge</span></span>        |
| <span data-ttu-id="ff7a6-116">Versión</span><span class="sxs-lookup"><span data-stu-id="ff7a6-116">Version</span></span> | <span data-ttu-id="ff7a6-117">4.5</span><span class="sxs-lookup"><span data-stu-id="ff7a6-117">4.5</span></span>         |
| <span data-ttu-id="ff7a6-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="ff7a6-118">Type</span></span>    | <span data-ttu-id="ff7a6-119">Redestinación</span><span class="sxs-lookup"><span data-stu-id="ff7a6-119">Retargeting</span></span> |
