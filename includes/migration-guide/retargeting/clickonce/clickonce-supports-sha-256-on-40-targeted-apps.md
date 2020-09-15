---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615744"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="6e17a-101">ClickOnce admite SHA-256 en aplicaciones destinadas a la versión 4.0</span><span class="sxs-lookup"><span data-stu-id="6e17a-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

#### <a name="details"></a><span data-ttu-id="6e17a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e17a-102">Details</span></span>

<span data-ttu-id="6e17a-103">Anteriormente, una aplicación ClickOnce con un certificado firmado con SHA-256 requería la presencia de .NET Framework 4.5 o una versión posterior, incluso si la aplicación se destinaba a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="6e17a-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="6e17a-104">Ahora, las aplicaciones ClickOnce destinadas a .NET Framework 4.0 se pueden ejecutar en .NET Framework 4.0, incluso si están firmadas con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="6e17a-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6e17a-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6e17a-105">Suggestion</span></span>

<span data-ttu-id="6e17a-106">Este cambio elimina esa dependencia y permite usar certificados de SHA-256 para firmar las aplicaciones ClickOnce que tienen como destino .NET Framework 4 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="6e17a-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>

| <span data-ttu-id="6e17a-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e17a-107">Name</span></span>    | <span data-ttu-id="6e17a-108">Valor</span><span class="sxs-lookup"><span data-stu-id="6e17a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6e17a-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6e17a-109">Scope</span></span>   | <span data-ttu-id="6e17a-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6e17a-110">Minor</span></span>       |
| <span data-ttu-id="6e17a-111">Versión</span><span class="sxs-lookup"><span data-stu-id="6e17a-111">Version</span></span> | <span data-ttu-id="6e17a-112">4.6</span><span class="sxs-lookup"><span data-stu-id="6e17a-112">4.6</span></span>         |
| <span data-ttu-id="6e17a-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e17a-113">Type</span></span>    | <span data-ttu-id="6e17a-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6e17a-114">Retargeting</span></span> |
