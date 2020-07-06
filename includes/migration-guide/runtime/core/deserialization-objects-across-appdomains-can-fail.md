---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620560"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="3ac8e-101">Se puede producir un error en la deserialización de objetos entre dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="3ac8e-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="3ac8e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3ac8e-102">Details</span></span>

<span data-ttu-id="3ac8e-103">En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="3ac8e-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3ac8e-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3ac8e-104">Suggestion</span></span>

<span data-ttu-id="3ac8e-105">Consulte [Mitigación: deserialización de objetos en distintos dominios de aplicación](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="3ac8e-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="3ac8e-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3ac8e-106">Name</span></span>    | <span data-ttu-id="3ac8e-107">Valor</span><span class="sxs-lookup"><span data-stu-id="3ac8e-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3ac8e-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3ac8e-108">Scope</span></span>   |<span data-ttu-id="3ac8e-109">Borde</span><span class="sxs-lookup"><span data-stu-id="3ac8e-109">Edge</span></span>|
|<span data-ttu-id="3ac8e-110">Versión</span><span class="sxs-lookup"><span data-stu-id="3ac8e-110">Version</span></span>|<span data-ttu-id="3ac8e-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3ac8e-111">4.5.1</span></span>|
|<span data-ttu-id="3ac8e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="3ac8e-112">Type</span></span>|<span data-ttu-id="3ac8e-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3ac8e-113">Runtime</span></span>|
