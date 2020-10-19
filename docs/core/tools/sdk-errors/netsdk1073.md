---
title: 'NETSDK1073: No se ha reconocido el valor de FrameworkReference'
description: Procedimiento para resolver el problema por el que no se puede encontrar el valor de FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957114"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="baf53-103">NETSDK1073: No se ha reconocido el valor de FrameworkReference</span><span class="sxs-lookup"><span data-stu-id="baf53-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="baf53-104">**Este artículo se aplica a:** ✔️ SDK de .NET 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="baf53-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="baf53-105">Normalmente este error significa que hay una versión de un elemento FrameworkReference concreto que el SDK no puede encontrar.</span><span class="sxs-lookup"><span data-stu-id="baf53-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="baf53-106">Intente eliminar las carpetas *obj* y *bin*, y ejecute `dotnet restore` para volver a descargar los paquetes de destino más recientes.</span><span class="sxs-lookup"><span data-stu-id="baf53-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="baf53-107">Como alternativa, es posible que haya un problema con la instalación, por lo que debe asegurarse de tener las versiones más recientes de .NET y Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="baf53-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
