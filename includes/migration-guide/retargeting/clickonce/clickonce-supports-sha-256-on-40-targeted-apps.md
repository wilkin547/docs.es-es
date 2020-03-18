---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804574"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="57a1f-101">ClickOnce admite SHA-256 en aplicaciones destinadas a la versión 4.0</span><span class="sxs-lookup"><span data-stu-id="57a1f-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="57a1f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="57a1f-102">Details</span></span>|<span data-ttu-id="57a1f-103">Anteriormente, una aplicación ClickOnce con un certificado firmado con SHA-256 requería la presencia de .NET Framework 4.5 o una versión posterior, incluso si la aplicación se destinaba a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="57a1f-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="57a1f-104">Ahora, las aplicaciones ClickOnce destinadas a .NET Framework 4.0 se pueden ejecutar en .NET Framework 4.0, incluso si están firmadas con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="57a1f-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="57a1f-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="57a1f-105">Suggestion</span></span>|<span data-ttu-id="57a1f-106">Este cambio elimina esa dependencia y permite usar certificados de SHA-256 para firmar las aplicaciones ClickOnce que tienen como destino .NET Framework 4 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="57a1f-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="57a1f-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="57a1f-107">Scope</span></span>|<span data-ttu-id="57a1f-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="57a1f-108">Minor</span></span>|
|<span data-ttu-id="57a1f-109">Versión</span><span class="sxs-lookup"><span data-stu-id="57a1f-109">Version</span></span>|<span data-ttu-id="57a1f-110">4.6</span><span class="sxs-lookup"><span data-stu-id="57a1f-110">4.6</span></span>|
|<span data-ttu-id="57a1f-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="57a1f-111">Type</span></span>|<span data-ttu-id="57a1f-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="57a1f-112">Retargeting</span></span>|
