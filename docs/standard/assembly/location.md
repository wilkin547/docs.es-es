---
title: Ubicación del ensamblado
description: La ubicación de un ensamblado .NET determina cómo lo encuentra CLR y si puede compartirse con otros ensamblados.
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 7ab3804b14b586e1430d654f4da32a310bcb6cc9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379895"
---
# <a name="assembly-location"></a><span data-ttu-id="e0c57-103">Ubicación del ensamblado</span><span class="sxs-lookup"><span data-stu-id="e0c57-103">Assembly location</span></span>
<span data-ttu-id="e0c57-104">La ubicación de un ensamblado determina si Common Language Runtime lo encontrará cuando se haga referencia a él y también puede determinar si el ensamblado se puede compartir con otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e0c57-104">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="e0c57-105">Puede implementar un ensamblado en las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0c57-105">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="e0c57-106">El directorio de la aplicación o subdirectorios de este.</span><span class="sxs-lookup"><span data-stu-id="e0c57-106">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="e0c57-107">Esta es la ubicación más común para implementar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e0c57-107">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="e0c57-108">Los subdirectorios del directorio raíz de la aplicación pueden basarse en un idioma o referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="e0c57-108">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="e0c57-109">Si un ensamblado tiene información en el atributo de referencia cultural, debe estar en un subdirectorio bajo el directorio de la aplicación con el nombre de esa referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="e0c57-109">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="e0c57-110">La caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e0c57-110">The global assembly cache.</span></span>

     <span data-ttu-id="e0c57-111">Se trata de una caché de código del equipo que se instala donde está instalado Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e0c57-111">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="e0c57-112">En la mayoría de los casos, si se piensa compartir un ensamblado entre varias aplicaciones, debe implementarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e0c57-112">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="e0c57-113">Un servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="e0c57-113">On an HTTP server.</span></span>

     <span data-ttu-id="e0c57-114">Un ensamblado implementado en un servidor HTTP debe tener un nombre seguro. Debe apuntar al ensamblado en la sección de código base del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0c57-114">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0c57-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0c57-115">See also</span></span>

- [<span data-ttu-id="e0c57-116">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="e0c57-116">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="e0c57-117">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="e0c57-117">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="e0c57-118">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="e0c57-118">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
