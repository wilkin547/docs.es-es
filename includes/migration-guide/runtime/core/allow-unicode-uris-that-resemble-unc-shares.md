---
ms.openlocfilehash: 3e8601ba76dfb05e3d70b3af7440bd7e228768d0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621369"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="6c4dc-101">Permitir Unicode en URI similares a los recursos compartidos UNC</span><span class="sxs-lookup"><span data-stu-id="6c4dc-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="6c4dc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6c4dc-102">Details</span></span>

<span data-ttu-id="6c4dc-103">En <xref:System.Uri?displayProperty=fullName>, la construcción de un URI que contenga un nombre de recurso compartido UNC y caracteres Unicode ya no dará como resultado un URI con el estado interno no válido.</span><span class="sxs-lookup"><span data-stu-id="6c4dc-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="6c4dc-104">El comportamiento solo cambiará cuando se cumpla todo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c4dc-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="6c4dc-105">El URI tiene el esquema <code>file:</code> y va seguido de cuatro o más barras diagonales.</span><span class="sxs-lookup"><span data-stu-id="6c4dc-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="6c4dc-106">El nombre de host comienza con un carácter de subrayado u otro símbolo no reservado.</span><span class="sxs-lookup"><span data-stu-id="6c4dc-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="6c4dc-107">El URI contiene caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="6c4dc-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="6c4dc-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6c4dc-108">Suggestion</span></span>

<span data-ttu-id="6c4dc-109">Las aplicaciones que trabajan con URI que contienen Unicode de forma coherente podrían haber usado este comportamiento para no permitir referencias a recursos compartidos UNC.</span><span class="sxs-lookup"><span data-stu-id="6c4dc-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="6c4dc-110">En su lugar, esas aplicaciones deben usar <xref:System.Uri.IsUnc>.</span><span class="sxs-lookup"><span data-stu-id="6c4dc-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="6c4dc-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6c4dc-111">Name</span></span>    | <span data-ttu-id="6c4dc-112">Valor</span><span class="sxs-lookup"><span data-stu-id="6c4dc-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6c4dc-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6c4dc-113">Scope</span></span>   |<span data-ttu-id="6c4dc-114">Borde</span><span class="sxs-lookup"><span data-stu-id="6c4dc-114">Edge</span></span>|
|<span data-ttu-id="6c4dc-115">Versión</span><span class="sxs-lookup"><span data-stu-id="6c4dc-115">Version</span></span>|<span data-ttu-id="6c4dc-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="6c4dc-116">4.7.2</span></span>|
|<span data-ttu-id="6c4dc-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c4dc-117">Type</span></span>|<span data-ttu-id="6c4dc-118">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6c4dc-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6c4dc-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6c4dc-119">Affected APIs</span></span>

-<xref:System.Uri?displayProperty=nameWithType></li></ul>|
