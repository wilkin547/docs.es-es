---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614773"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="65e22-101">Resgen rechaza la carga de contenido desde la web.</span><span class="sxs-lookup"><span data-stu-id="65e22-101">Resgen refuses to load content from the web</span></span>

#### <a name="details"></a><span data-ttu-id="65e22-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="65e22-102">Details</span></span>

<span data-ttu-id="65e22-103">Los archivos .resx pueden contener entradas con formato binario.</span><span class="sxs-lookup"><span data-stu-id="65e22-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="65e22-104">Si intenta usar resgen para cargar un archivo que se descargó desde una ubicación que no es de confianza, se producirá un error al cargar la entrada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="65e22-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65e22-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="65e22-105">Suggestion</span></span>

<span data-ttu-id="65e22-106">Los usuarios de resgen que necesiten cargar entradas con formato binario desde ubicaciones no confiables pueden eliminar la marca de la web del archivo de entrada o aplicar la opción de exclusión en toda la máquina: [HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span><span class="sxs-lookup"><span data-stu-id="65e22-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>

| <span data-ttu-id="65e22-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="65e22-107">Name</span></span>    | <span data-ttu-id="65e22-108">Valor</span><span class="sxs-lookup"><span data-stu-id="65e22-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65e22-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="65e22-109">Scope</span></span>   | <span data-ttu-id="65e22-110">Borde</span><span class="sxs-lookup"><span data-stu-id="65e22-110">Edge</span></span>        |
| <span data-ttu-id="65e22-111">Versión</span><span class="sxs-lookup"><span data-stu-id="65e22-111">Version</span></span> | <span data-ttu-id="65e22-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="65e22-112">4.7.2</span></span>       |
| <span data-ttu-id="65e22-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="65e22-113">Type</span></span>    | <span data-ttu-id="65e22-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="65e22-114">Retargeting</span></span> |
