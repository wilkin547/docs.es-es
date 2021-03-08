---
ms.openlocfilehash: 5a027054024d8429831d73525ab3748c51ae850e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255766"
---

<span data-ttu-id="663a9-101">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="663a9-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="663a9-102">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="663a9-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="663a9-103">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="663a9-103">krb5-libs</span></span>
- <span data-ttu-id="663a9-104">libicu</span><span class="sxs-lookup"><span data-stu-id="663a9-104">libicu</span></span>
- <span data-ttu-id="663a9-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="663a9-105">openssl-libs</span></span>
- <span data-ttu-id="663a9-106">zlib</span><span class="sxs-lookup"><span data-stu-id="663a9-106">zlib</span></span>

<span data-ttu-id="663a9-107">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="663a9-107">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="663a9-108">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="663a9-108">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="663a9-109">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="663a9-109">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="663a9-110">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="663a9-110">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="663a9-111">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="663a9-111">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="663a9-112">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="663a9-112">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
