---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497141"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="2aae4-101">Permitir Unicode en URI similares a los recursos compartidos UNC</span><span class="sxs-lookup"><span data-stu-id="2aae4-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="2aae4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="2aae4-102">Details</span></span>

<span data-ttu-id="2aae4-103">En <xref:System.Uri?displayProperty=fullName>, la construcción de un URI que contenga un nombre de recurso compartido UNC y caracteres Unicode ya no dará como resultado un URI con el estado interno no válido.</span><span class="sxs-lookup"><span data-stu-id="2aae4-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="2aae4-104">El comportamiento solo cambiará cuando se cumpla todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aae4-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="2aae4-105">El URI tiene el esquema <code>file:</code> y va seguido de cuatro o más barras diagonales.</span><span class="sxs-lookup"><span data-stu-id="2aae4-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="2aae4-106">El nombre de host comienza con un carácter de subrayado u otro símbolo no reservado.</span><span class="sxs-lookup"><span data-stu-id="2aae4-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="2aae4-107">El URI contiene caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="2aae4-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="2aae4-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="2aae4-108">Suggestion</span></span>

<span data-ttu-id="2aae4-109">Las aplicaciones que trabajan con URI que contienen Unicode de forma coherente podrían haber usado este comportamiento para no permitir referencias a recursos compartidos UNC.</span><span class="sxs-lookup"><span data-stu-id="2aae4-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="2aae4-110">En su lugar, esas aplicaciones deben usar <xref:System.Uri.IsUnc>.</span><span class="sxs-lookup"><span data-stu-id="2aae4-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="2aae4-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="2aae4-111">Name</span></span>    | <span data-ttu-id="2aae4-112">Valor</span><span class="sxs-lookup"><span data-stu-id="2aae4-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2aae4-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="2aae4-113">Scope</span></span>   |<span data-ttu-id="2aae4-114">Borde</span><span class="sxs-lookup"><span data-stu-id="2aae4-114">Edge</span></span>|
|<span data-ttu-id="2aae4-115">Versión</span><span class="sxs-lookup"><span data-stu-id="2aae4-115">Version</span></span>|<span data-ttu-id="2aae4-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="2aae4-116">4.7.2</span></span>|
|<span data-ttu-id="2aae4-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="2aae4-117">Type</span></span>|<span data-ttu-id="2aae4-118">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2aae4-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2aae4-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2aae4-119">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
