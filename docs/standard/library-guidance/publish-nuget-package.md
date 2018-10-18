---
title: Publicación de un paquete de NuGet
description: Prácticas recomendadas para la publicación de las bibliotecas de .NET en NuGet.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 0602712311411ef3d59825bec8c5e550bc8d8265
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370324"
---
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="4ba17-103">Publicación de un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="4ba17-103">Publishing a NuGet package</span></span>

<span data-ttu-id="4ba17-104">Paquetes de NuGet se publican y se consume desde repositorios de paquetes.</span><span class="sxs-lookup"><span data-stu-id="4ba17-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="4ba17-105">Aunque NuGet.org es más ampliamente repositorio utilizan y conocen, hay muchos lugares para publicar paquetes de NuGet:</span><span class="sxs-lookup"><span data-stu-id="4ba17-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="4ba17-106">**[NuGet.org](https://www.nuget.org/)**  es el repositorio principal en línea para los paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4ba17-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="4ba17-107">Todos los paquetes en NuGet.org están disponibles públicamente para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4ba17-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="4ba17-108">De forma predeterminada, Visual Studio tiene NuGet.org como un origen del paquete y para muchos desarrolladores NuGet.org es el repositorio de paquetes solo con que podrá interactuar.</span><span class="sxs-lookup"><span data-stu-id="4ba17-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="4ba17-109">NuGet.org es el mejor lugar para publicar los paquetes estables y paquetes de versión preliminar que desee que los comentarios de la Comunidad en.</span><span class="sxs-lookup"><span data-stu-id="4ba17-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="4ba17-110">**[MyGet](https://myget.org/)**  repositorio service admite [fuentes de distribución de paquete personalizado gratuito para proyectos de código abierto](https://www.myget.org/opensource).</span><span class="sxs-lookup"><span data-stu-id="4ba17-110">**[MyGet](https://myget.org/)** repository service supports [free custom package feeds for open-source projects](https://www.myget.org/opensource).</span></span> <span data-ttu-id="4ba17-111">Una fuente personalizada pública de MyGet es un lugar ideal para publicar paquetes de versión preliminar creados por el servicio de integración continua.</span><span class="sxs-lookup"><span data-stu-id="4ba17-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="4ba17-112">MyGet también proporciona fuentes privadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="4ba17-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="4ba17-113">Un **[fuente local](/nuget/hosting-packages/local-feeds)** permite tratar una carpeta como un repositorio de paquetes y hace que el `*.nupkg` archivos en la carpeta accesible mediante NuGet.</span><span class="sxs-lookup"><span data-stu-id="4ba17-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="4ba17-114">Una fuente local es útil para probar un paquete de NuGet antes de publicarlo en NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="4ba17-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="4ba17-115">NuGet.org [no permite un paquete que se va a eliminar](/nuget/policies/deleting-packages) después de que se cargue.</span><span class="sxs-lookup"><span data-stu-id="4ba17-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="4ba17-116">Un paquete puede ser dados de baja para que no sea visible públicamente en la interfaz de usuario, pero la `*.nupkg` puede descargarse en la restauración.</span><span class="sxs-lookup"><span data-stu-id="4ba17-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="4ba17-117">Además, nuget.org no admite versiones de paquetes duplicados.</span><span class="sxs-lookup"><span data-stu-id="4ba17-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="4ba17-118">Para corregir un paquete de NuGet con un error que tendrá que quitar de la lista el paquete incorrecto, incremente el número de versión y publique una nueva versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="4ba17-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="4ba17-119">**HACER ✔️** [publicar los paquetes estables y paquetes de versión preliminar](/nuget/create-packages/publish-a-package) desea que los comentarios de la Comunidad en NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="4ba17-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="4ba17-120">**Considere la posibilidad de ✔️** publicar paquetes de versión preliminar en un MyGet fuente desde una compilación de integración continua.</span><span class="sxs-lookup"><span data-stu-id="4ba17-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="4ba17-121">**Considere la posibilidad de ✔️** probar paquetes en su entorno de desarrollo mediante una fuente local o MyGet.</span><span class="sxs-lookup"><span data-stu-id="4ba17-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="4ba17-122">Compruebe las obras de paquete, a continuación, publicarlo en NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="4ba17-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="4ba17-123">Seguridad de NuGet.org</span><span class="sxs-lookup"><span data-stu-id="4ba17-123">NuGet.org security</span></span>

<span data-ttu-id="4ba17-124">Es importante que los actores no válidos no se puede acceder a su cuenta de NuGet y cargar una versión de la biblioteca malintencionada.</span><span class="sxs-lookup"><span data-stu-id="4ba17-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="4ba17-125">NuGet.org ofrece notificaciones de correo electrónico y la autenticación de dos fases cuando se publica un paquete.</span><span class="sxs-lookup"><span data-stu-id="4ba17-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="4ba17-126">Habilitar estas características tras iniciar sesión en NuGet.org en el **configuración de la cuenta** página.</span><span class="sxs-lookup"><span data-stu-id="4ba17-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="4ba17-127">![texto alternativo](./media/publish-nuget-package/nuget-2fa.png "seguridad de la cuenta de NuGet")</span><span class="sxs-lookup"><span data-stu-id="4ba17-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="4ba17-128">**HACER ✔️** usar una cuenta de Microsoft para iniciar sesión NuGet.</span><span class="sxs-lookup"><span data-stu-id="4ba17-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="4ba17-129">**HACER ✔️** habilitar la autenticación en dos fases para acceder a NuGet.</span><span class="sxs-lookup"><span data-stu-id="4ba17-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="4ba17-130">**HACER ✔️** Habilitar notificación por correo electrónico cuando se publica un paquete.</span><span class="sxs-lookup"><span data-stu-id="4ba17-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="4ba17-131">[Anterior](./sourcelink.md)
[Siguiente](./versioning.md)</span><span class="sxs-lookup"><span data-stu-id="4ba17-131">[Previous](./sourcelink.md)
[Next](./versioning.md)</span></span>
