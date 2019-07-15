---
ms.openlocfilehash: 9bf6972812bdf4a385b99fe34d2cd3cd8a91c8cf
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804574"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="8db2d-101">ClickOnce admite SHA-256 en aplicaciones destinadas a la versión 4.0</span><span class="sxs-lookup"><span data-stu-id="8db2d-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8db2d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8db2d-102">Details</span></span>|<span data-ttu-id="8db2d-103">Anteriormente, una aplicación ClickOnce con un certificado firmado con SHA-256 requería la presencia de .NET Framework 4.5 o una versión posterior, incluso si la aplicación se destinaba a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="8db2d-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="8db2d-104">Ahora, las aplicaciones ClickOnce destinadas a .NET Framework 4.0 se pueden ejecutar en .NET Framework 4.0, incluso si están firmadas con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="8db2d-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="8db2d-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8db2d-105">Suggestion</span></span>|<span data-ttu-id="8db2d-106">Este cambio elimina esa dependencia y permite usar certificados de SHA-256 para firmar las aplicaciones ClickOnce que tienen como destino .NET Framework 4 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8db2d-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="8db2d-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8db2d-107">Scope</span></span>|<span data-ttu-id="8db2d-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8db2d-108">Minor</span></span>|
|<span data-ttu-id="8db2d-109">Versión</span><span class="sxs-lookup"><span data-stu-id="8db2d-109">Version</span></span>|<span data-ttu-id="8db2d-110">4.6</span><span class="sxs-lookup"><span data-stu-id="8db2d-110">4.6</span></span>|
|<span data-ttu-id="8db2d-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="8db2d-111">Type</span></span>|<span data-ttu-id="8db2d-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="8db2d-112">Retargeting</span></span>|

